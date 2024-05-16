Package sql
===========

-   `import "database/sql"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)
-   [Subdirectories](#pkg-subdirectories)

Overview 
--------

Package sql provides a generic interface around SQL (or SQL-like)
databases.

The sql package must be used in conjunction with a database driver. See
https://golang.org/s/sqldrivers> for a list of drivers.

Drivers that do not support context cancellation will not return until
after the query is completed.

For usage examples, see the wiki page at https://golang.org/s/sqlwiki>.

#### [Example (OpenDBCLI)]

Code:

```go
package sql_test

import (
    "context"
    "database/sql"
    "flag"
    "log"
    "os"
    "os/signal"
    "time"
)

var pool *sql.DB // Database connection pool.

func Example_openDBCLI() {
    id := flag.Int64("id", 0, "person ID to find")
    dsn := flag.String("dsn", os.Getenv("DSN"), "connection data source name")
    flag.Parse()

    if len(*dsn) == 0 {
        log.Fatal("missing dsn flag")
    }
    if *id == 0 {
        log.Fatal("missing person ID")
    }
    var err error

    // Opening a driver typically will not attempt to connect to the database.
    pool, err = sql.Open("driver-name", *dsn)
    if err != nil {
        // This will not be a connection error, but a DSN parse error or
        // another initialization error.
        log.Fatal("unable to use data source name", err)
    }
    defer pool.Close()

    pool.SetConnMaxLifetime(0)
    pool.SetMaxIdleConns(3)
    pool.SetMaxOpenConns(3)

    ctx, stop := context.WithCancel(context.Background())
    defer stop()

    appSignal := make(chan os.Signal, 3)
    signal.Notify(appSignal, os.Interrupt)

    go func() {
        <-appSignal
        stop()
    }()

    Ping(ctx)

    Query(ctx, *id)
}

// Ping the database to verify DSN provided by the user is valid and the
// server accessible. If the ping fails exit the program with an error.
func Ping(ctx context.Context) {
    ctx, cancel := context.WithTimeout(ctx, 1*time.Second)
    defer cancel()

    if err := pool.PingContext(ctx); err != nil {
        log.Fatalf("unable to connect to database: %v", err)
    }
}

// Query the database for the information requested and prints the results.
// If the query fails exit the program with an error.
func Query(ctx context.Context, id int64) {
    ctx, cancel := context.WithTimeout(ctx, 5*time.Second)
    defer cancel()

    var name string
    err := pool.QueryRowContext(ctx, "select p.name from people as p where p.id = :id;", sql.Named("id", id)).Scan(&name)
    if err != nil {
        log.Fatal("unable to execute search query", err)
    }
    log.Println("name=", name)
}
```

#### [Example (OpenDBService)]

Code:

```go
package sql_test

import (
    "context"
    "database/sql"
    "encoding/json"
    "fmt"
    "io"
    "log"
    "net/http"
    "time"
)

func Example_openDBService() {
    // Opening a driver typically will not attempt to connect to the database.
    db, err := sql.Open("driver-name", "database=test1")
    if err != nil {
        // This will not be a connection error, but a DSN parse error or
        // another initialization error.
        log.Fatal(err)
    }
    db.SetConnMaxLifetime(0)
    db.SetMaxIdleConns(50)
    db.SetMaxOpenConns(50)

    s := &Service{db: db}

    http.ListenAndServe(":8080", s)
}

type Service struct {
    db *sql.DB
}

func (s *Service) ServeHTTP(w http.ResponseWriter, r *http.Request) {
    db := s.db
    switch r.URL.Path {
    default:
        http.Error(w, "not found", http.StatusNotFound)
        return
    case "/healthz":
        ctx, cancel := context.WithTimeout(r.Context(), 1*time.Second)
        defer cancel()

        err := s.db.PingContext(ctx)
        if err != nil {
            http.Error(w, fmt.Sprintf("db down: %v", err), http.StatusFailedDependency)
            return
        }
        w.WriteHeader(http.StatusOK)
        return
    case "/quick-action":
        // This is a short SELECT. Use the request context as the base of
        // the context timeout.
        ctx, cancel := context.WithTimeout(r.Context(), 3*time.Second)
        defer cancel()

        id := 5
        org := 10
        var name string
        err := db.QueryRowContext(ctx, `
select
    p.name
from
    people as p
    join organization as o on p.organization = o.id
where
    p.id = :id
    and o.id = :org
;`,
            sql.Named("id", id),
            sql.Named("org", org),
        ).Scan(&name)
        if err != nil {
            if err == sql.ErrNoRows {
                http.Error(w, "not found", http.StatusNotFound)
                return
            }
            http.Error(w, err.Error(), http.StatusInternalServerError)
            return
        }
        io.WriteString(w, name)
        return
    case "/long-action":
        // This is a long SELECT. Use the request context as the base of
        // the context timeout, but give it some time to finish. If
        // the client cancels before the query is done the query will also
        // be canceled.
        ctx, cancel := context.WithTimeout(r.Context(), 60*time.Second)
        defer cancel()

        var names []string
        rows, err := db.QueryContext(ctx, "select p.name from people as p where p.active = true;")
        if err != nil {
            http.Error(w, err.Error(), http.StatusInternalServerError)
            return
        }

        for rows.Next() {
            var name string
            err = rows.Scan(&name)
            if err != nil {
                break
            }
            names = append(names, name)
        }
        // Check for errors during rows "Close".
        // This may be more important if multiple statements are executed
        // in a single batch and rows were written as well as read.
        if closeErr := rows.Close(); closeErr != nil {
            http.Error(w, closeErr.Error(), http.StatusInternalServerError)
            return
        }

        // Check for row scan error.
        if err != nil {
            http.Error(w, err.Error(), http.StatusInternalServerError)
            return
        }

        // Check for errors during row iteration.
        if err = rows.Err(); err != nil {
            http.Error(w, err.Error(), http.StatusInternalServerError)
            return
        }

        json.NewEncoder(w).Encode(names)
        return
    case "/async-action":
        // This action has side effects that we want to preserve
        // even if the client cancels the HTTP request part way through.
        // For this we do not use the http request context as a base for
        // the timeout.
        ctx, cancel := context.WithTimeout(context.Background(), 10*time.Second)
        defer cancel()

        var orderRef = "ABC123"
        tx, err := db.BeginTx(ctx, &sql.TxOptions{Isolation: sql.LevelSerializable})
        _, err = tx.ExecContext(ctx, "stored_proc_name", orderRef)

        if err != nil {
            tx.Rollback()
            http.Error(w, err.Error(), http.StatusInternalServerError)
            return
        }
        err = tx.Commit()
        if err != nil {
            http.Error(w, "action in unknown state, check state before attempting again", http.StatusInternalServerError)
            return
        }
        w.WriteHeader(http.StatusOK)
        return
    }
}
```

Index 
-----

-   [Variables](#pkg-variables)
-   [func Drivers() \[\]string](#Drivers)
-   [func Register(name string, driver driver.Driver)](#Register)
-   [type ColumnType](#ColumnType)
-   [func (ci \*ColumnType) DatabaseTypeName()
    string](#ColumnType.DatabaseTypeName)
-   [func (ci \*ColumnType) DecimalSize() (precision, scale int64, ok
    bool)](#ColumnType.DecimalSize)
-   [func (ci \*ColumnType) Length() (length int64, ok
    bool)](#ColumnType.Length)
-   [func (ci \*ColumnType) Name() string](#ColumnType.Name)
-   [func (ci \*ColumnType) Nullable() (nullable, ok
    bool)](#ColumnType.Nullable)
-   [func (ci \*ColumnType) ScanType()
    reflect.Type](#ColumnType.ScanType)
-   [type Conn](#Conn)
-   [func (c \*Conn) BeginTx(ctx context.Context, opts \*TxOptions)
    (\*Tx, error)](#Conn.BeginTx)
-   [func (c \*Conn) Close() error](#Conn.Close)
-   [func (c \*Conn) ExecContext(ctx context.Context, query string, args
    \...any) (Result, error)](#Conn.ExecContext)
-   [func (c \*Conn) PingContext(ctx context.Context)
    error](#Conn.PingContext)
-   [func (c \*Conn) PrepareContext(ctx context.Context, query string)
    (\*Stmt, error)](#Conn.PrepareContext)
-   [func (c \*Conn) QueryContext(ctx context.Context, query string,
    args \...any) (\*Rows, error)](#Conn.QueryContext)
-   [func (c \*Conn) QueryRowContext(ctx context.Context, query string,
    args \...any) \*Row](#Conn.QueryRowContext)
-   [func (c \*Conn) Raw(f func(driverConn any) error) (err
    error)](#Conn.Raw)
-   [type DB](#DB)
-   [func Open(driverName, dataSourceName string) (\*DB, error)](#Open)
-   [func OpenDB(c driver.Connector) \*DB](#OpenDB)
-   [func (db \*DB) Begin() (\*Tx, error)](#DB.Begin)
-   [func (db \*DB) BeginTx(ctx context.Context, opts \*TxOptions)
    (\*Tx, error)](#DB.BeginTx)
-   [func (db \*DB) Close() error](#DB.Close)
-   [func (db \*DB) Conn(ctx context.Context) (\*Conn, error)](#DB.Conn)
-   [func (db \*DB) Driver() driver.Driver](#DB.Driver)
-   [func (db \*DB) Exec(query string, args \...any) (Result,
    error)](#DB.Exec)
-   [func (db \*DB) ExecContext(ctx context.Context, query string, args
    \...any) (Result, error)](#DB.ExecContext)
-   [func (db \*DB) Ping() error](#DB.Ping)
-   [func (db \*DB) PingContext(ctx context.Context)
    error](#DB.PingContext)
-   [func (db \*DB) Prepare(query string) (\*Stmt, error)](#DB.Prepare)
-   [func (db \*DB) PrepareContext(ctx context.Context, query string)
    (\*Stmt, error)](#DB.PrepareContext)
-   [func (db \*DB) Query(query string, args \...any) (\*Rows,
    error)](#DB.Query)
-   [func (db \*DB) QueryContext(ctx context.Context, query string, args
    \...any) (\*Rows, error)](#DB.QueryContext)
-   [func (db \*DB) QueryRow(query string, args \...any)
    \*Row](#DB.QueryRow)
-   [func (db \*DB) QueryRowContext(ctx context.Context, query string,
    args \...any) \*Row](#DB.QueryRowContext)
-   [func (db \*DB) SetConnMaxIdleTime(d
    time.Duration)](#DB.SetConnMaxIdleTime)
-   [func (db \*DB) SetConnMaxLifetime(d
    time.Duration)](#DB.SetConnMaxLifetime)
-   [func (db \*DB) SetMaxIdleConns(n int)](#DB.SetMaxIdleConns)
-   [func (db \*DB) SetMaxOpenConns(n int)](#DB.SetMaxOpenConns)
-   [func (db \*DB) Stats() DBStats](#DB.Stats)
-   [type DBStats](#DBStats)
-   [type IsolationLevel](#IsolationLevel)
-   [func (i IsolationLevel) String() string](#IsolationLevel.String)
-   [type NamedArg](#NamedArg)
-   [func Named(name string, value any) NamedArg](#Named)
-   [type NullBool](#NullBool)
-   [func (n \*NullBool) Scan(value any) error](#NullBool.Scan)
-   [func (n NullBool) Value() (driver.Value, error)](#NullBool.Value)
-   [type NullByte](#NullByte)
-   [func (n \*NullByte) Scan(value any) error](#NullByte.Scan)
-   [func (n NullByte) Value() (driver.Value, error)](#NullByte.Value)
-   [type NullFloat64](#NullFloat64)
-   [func (n \*NullFloat64) Scan(value any) error](#NullFloat64.Scan)
-   [func (n NullFloat64) Value() (driver.Value,
    error)](#NullFloat64.Value)
-   [type NullInt16](#NullInt16)
-   [func (n \*NullInt16) Scan(value any) error](#NullInt16.Scan)
-   [func (n NullInt16) Value() (driver.Value, error)](#NullInt16.Value)
-   [type NullInt32](#NullInt32)
-   [func (n \*NullInt32) Scan(value any) error](#NullInt32.Scan)
-   [func (n NullInt32) Value() (driver.Value, error)](#NullInt32.Value)
-   [type NullInt64](#NullInt64)
-   [func (n \*NullInt64) Scan(value any) error](#NullInt64.Scan)
-   [func (n NullInt64) Value() (driver.Value, error)](#NullInt64.Value)
-   [type NullString](#NullString)
-   [func (ns \*NullString) Scan(value any) error](#NullString.Scan)
-   [func (ns NullString) Value() (driver.Value,
    error)](#NullString.Value)
-   [type NullTime](#NullTime)
-   [func (n \*NullTime) Scan(value any) error](#NullTime.Scan)
-   [func (n NullTime) Value() (driver.Value, error)](#NullTime.Value)
-   [type Out](#Out)
-   [type RawBytes](#RawBytes)
-   [type Result](#Result)
-   [type Row](#Row)
-   [func (r \*Row) Err() error](#Row.Err)
-   [func (r \*Row) Scan(dest \...any) error](#Row.Scan)
-   [type Rows](#Rows)
-   [func (rs \*Rows) Close() error](#Rows.Close)
-   [func (rs \*Rows) ColumnTypes() (\[\]\*ColumnType,
    error)](#Rows.ColumnTypes)
-   [func (rs \*Rows) Columns() (\[\]string, error)](#Rows.Columns)
-   [func (rs \*Rows) Err() error](#Rows.Err)
-   [func (rs \*Rows) Next() bool](#Rows.Next)
-   [func (rs \*Rows) NextResultSet() bool](#Rows.NextResultSet)
-   [func (rs \*Rows) Scan(dest \...any) error](#Rows.Scan)
-   [type Scanner](#Scanner)
-   [type Stmt](#Stmt)
-   [func (s \*Stmt) Close() error](#Stmt.Close)
-   [func (s \*Stmt) Exec(args \...any) (Result, error)](#Stmt.Exec)
-   [func (s \*Stmt) ExecContext(ctx context.Context, args \...any)
    (Result, error)](#Stmt.ExecContext)
-   [func (s \*Stmt) Query(args \...any) (\*Rows, error)](#Stmt.Query)
-   [func (s \*Stmt) QueryContext(ctx context.Context, args \...any)
    (\*Rows, error)](#Stmt.QueryContext)
-   [func (s \*Stmt) QueryRow(args \...any) \*Row](#Stmt.QueryRow)
-   [func (s \*Stmt) QueryRowContext(ctx context.Context, args \...any)
    \*Row](#Stmt.QueryRowContext)
-   [type Tx](#Tx)
-   [func (tx \*Tx) Commit() error](#Tx.Commit)
-   [func (tx \*Tx) Exec(query string, args \...any) (Result,
    error)](#Tx.Exec)
-   [func (tx \*Tx) ExecContext(ctx context.Context, query string, args
    \...any) (Result, error)](#Tx.ExecContext)
-   [func (tx \*Tx) Prepare(query string) (\*Stmt, error)](#Tx.Prepare)
-   [func (tx \*Tx) PrepareContext(ctx context.Context, query string)
    (\*Stmt, error)](#Tx.PrepareContext)
-   [func (tx \*Tx) Query(query string, args \...any) (\*Rows,
    error)](#Tx.Query)
-   [func (tx \*Tx) QueryContext(ctx context.Context, query string, args
    \...any) (\*Rows, error)](#Tx.QueryContext)
-   [func (tx \*Tx) QueryRow(query string, args \...any)
    \*Row](#Tx.QueryRow)
-   [func (tx \*Tx) QueryRowContext(ctx context.Context, query string,
    args \...any) \*Row](#Tx.QueryRowContext)
-   [func (tx \*Tx) Rollback() error](#Tx.Rollback)
-   [func (tx \*Tx) Stmt(stmt \*Stmt) \*Stmt](#Tx.Stmt)
-   [func (tx \*Tx) StmtContext(ctx context.Context, stmt \*Stmt)
    \*Stmt](#Tx.StmtContext)
-   [type TxOptions](#TxOptions)

 
### Examples

[Conn.ExecContext](#example_Conn_ExecContext)

[DB.BeginTx](#example_DB_BeginTx)

[DB.ExecContext](#example_DB_ExecContext)

[DB.PingContext](#example_DB_PingContext)

[DB.Prepare](#example_DB_Prepare)

[DB.QueryContext](#example_DB_QueryContext)

[DB.QueryRowContext](#example_DB_QueryRowContext)

[DB.Query
(MultipleResultSets)](#example_DB_Query_multipleResultSets)

[Rows](#example_Rows)

[Stmt](#example_Stmt)

[Stmt.QueryRowContext](#example_Stmt_QueryRowContext)

[Tx.ExecContext](#example_Tx_ExecContext)

[Tx.Prepare](#example_Tx_Prepare)

[Tx.Rollback](#example_Tx_Rollback)

[Package (OpenDBCLI)](#example__openDBCLI)

[Package (OpenDBService)](#example__openDBService)


### Package files

convert.go ctxutil.go sql.go

Variables 
---------

ErrConnDone is returned by any operation that is performed on a
connection that has already been returned to the connection pool.

```go
var ErrConnDone = errors.New("sql: connection is already closed")
```

ErrNoRows is returned by Scan when QueryRow doesn\'t return a row. In
such a case, QueryRow returns a placeholder \*Row value that defers this
error until a Scan.

```go
var ErrNoRows = errors.New("sql: no rows in result set")
```

ErrTxDone is returned by any operation that is performed on a
transaction that has already been committed or rolled back.

```go
var ErrTxDone = errors.New("sql: transaction has already been committed or rolled back")
```

func Drivers 
-------------------------------------------

```go
func Drivers() []string
```

Drivers returns a sorted list of the names of the registered drivers.

func Register 
-------------

```go
func Register(name string, driver driver.Driver)
```

Register makes a database driver available by the provided name. If
Register is called twice with the same name or if driver is nil, it
panics.

type ColumnType 
----------------------------------------------

ColumnType contains the name and type of a column.

```go
type ColumnType struct {
    // contains filtered or unexported fields
}
```

### func (\*ColumnType) DatabaseTypeName 

```go
func (ci *ColumnType) DatabaseTypeName() string
```

DatabaseTypeName returns the database system name of the column type. If
an empty string is returned, then the driver type name is not supported.
Consult your driver documentation for a list of driver data types.
Length specifiers are not included. Common type names include
\"VARCHAR\", \"TEXT\", \"NVARCHAR\", \"DECIMAL\", \"BOOL\", \"INT\", and
\"BIGINT\".

### func (\*ColumnType) DecimalSize 

```go
func (ci *ColumnType) DecimalSize() (precision, scale int64, ok bool)
```

DecimalSize returns the scale and precision of a decimal type. If not
applicable or if not supported ok is false.

### func (\*ColumnType) Length 

```go
func (ci *ColumnType) Length() (length int64, ok bool)
```

Length returns the column type length for variable length column types
such as text and binary field types. If the type length is unbounded the
value will be math.MaxInt64 (any database limits will still apply). If
the column type is not variable length, such as an int, or if not
supported by the driver ok is false.

### func (\*ColumnType) Name 

```go
func (ci *ColumnType) Name() string
```

Name returns the name or alias of the column.

### func (\*ColumnType) Nullable 

```go
func (ci *ColumnType) Nullable() (nullable, ok bool)
```

Nullable reports whether the column may be null. If a driver does not
support this property ok will be false.

### func (\*ColumnType) ScanType 

```go
func (ci *ColumnType) ScanType() reflect.Type
```

ScanType returns a Go type suitable for scanning into using Rows.Scan.
If a driver does not support this property ScanType will return the type
of an empty interface.

type Conn 
----------------------------------------

Conn represents a single database connection rather than a pool of
database connections. Prefer running queries from DB unless there is a
specific need for a continuous single database connection.

A Conn must call Close to return the connection to the database pool and
may do so concurrently with a running query.

After a call to Close, all operations on the connection fail with
ErrConnDone.

```go
type Conn struct {
    // contains filtered or unexported fields
}
```

### func (\*Conn) BeginTx 

```go
func (c *Conn) BeginTx(ctx context.Context, opts *TxOptions) (*Tx, error)
```

BeginTx starts a transaction.

The provided context is used until the transaction is committed or
rolled back. If the context is canceled, the sql package will roll back
the transaction. Tx.Commit will return an error if the context provided
to BeginTx is canceled.

The provided TxOptions is optional and may be nil if defaults should be
used. If a non-default isolation level is used that the driver doesn\'t
support, an error will be returned.

### func (\*Conn) Close 

```go
func (c *Conn) Close() error
```

Close returns the connection to the connection pool. All operations
after a Close will return with ErrConnDone. Close is safe to call
concurrently with other operations and will block until all other
operations finish. It may be useful to first cancel any used context and
then call close directly after.

### func (\*Conn) ExecContext 

```go
func (c *Conn) ExecContext(ctx context.Context, query string, args ...any) (Result, error)
```

ExecContext executes a query without returning any rows. The args are
for any placeholder parameters in the query.

#### [Example]

Code:

```go
// A *DB is a pool of connections. Call Conn to reserve a connection for
// exclusive use.
conn, err := db.Conn(ctx)
if err != nil {
    log.Fatal(err)
}
defer conn.Close() // Return the connection to the pool.
id := 41
result, err := conn.ExecContext(ctx, `UPDATE balances SET balance = balance + 10 WHERE user_id = ?;`, id)
if err != nil {
    log.Fatal(err)
}
rows, err := result.RowsAffected()
if err != nil {
    log.Fatal(err)
}
if rows != 1 {
    log.Fatalf("expected single row affected, got %d rows affected", rows)
}
```

### func (\*Conn) PingContext 

```go
func (c *Conn) PingContext(ctx context.Context) error
```

PingContext verifies the connection to the database is still alive.

### func (\*Conn) PrepareContext 

```go
func (c *Conn) PrepareContext(ctx context.Context, query string) (*Stmt, error)
```

PrepareContext creates a prepared statement for later queries or
executions. Multiple queries or executions may be run concurrently from
the returned statement. The caller must call the statement\'s Close
method when the statement is no longer needed.

The provided context is used for the preparation of the statement, not
for the execution of the statement.

### func (\*Conn) QueryContext 

```go
func (c *Conn) QueryContext(ctx context.Context, query string, args ...any) (*Rows, error)
```

QueryContext executes a query that returns rows, typically a SELECT. The
args are for any placeholder parameters in the query.

### func (\*Conn) QueryRowContext 

```go
func (c *Conn) QueryRowContext(ctx context.Context, query string, args ...any) *Row
```

QueryRowContext executes a query that is expected to return at most one
row. QueryRowContext always returns a non-nil value. Errors are deferred
until Row\'s Scan method is called. If the query selects no rows, the
\*Row\'s Scan will return ErrNoRows. Otherwise, the \*Row\'s Scan scans
the first selected row and discards the rest.

### func (\*Conn) Raw 

```go
func (c *Conn) Raw(f func(driverConn any) error) (err error)
```

Raw executes f exposing the underlying driver connection for the
duration of f. The driverConn must not be used outside of f.

Once f returns and err is not driver.ErrBadConn, the Conn will continue
to be usable until Conn.Close is called.

type DB 
-------

DB is a database handle representing a pool of zero or more underlying
connections. It\'s safe for concurrent use by multiple goroutines.

The sql package creates and frees connections automatically; it also
maintains a free pool of idle connections. If the database has a concept
of per-connection state, such state can be reliably observed within a
transaction (Tx) or connection (Conn). Once DB.Begin is called, the
returned Tx is bound to a single connection. Once Commit or Rollback is
called on the transaction, that transaction\'s connection is returned to
DB\'s idle connection pool. The pool size can be controlled with
SetMaxIdleConns.

```go
type DB struct {
    // contains filtered or unexported fields
}
```

### func Open 

```go
func Open(driverName, dataSourceName string) (*DB, error)
```

Open opens a database specified by its database driver name and a
driver-specific data source name, usually consisting of at least a
database name and connection information.

Most users will open a database via a driver-specific connection helper
function that returns a \*DB. No database drivers are included in the Go
standard library. See https://golang.org/s/sqldrivers> for a list of
third-party drivers.

Open may just validate its arguments without creating a connection to
the database. To verify that the data source name is valid, call Ping.

The returned DB is safe for concurrent use by multiple goroutines and
maintains its own pool of idle connections. Thus, the Open function
should be called just once. It is rarely necessary to close a DB.

### func OpenDB 

```go
func OpenDB(c driver.Connector) *DB
```

OpenDB opens a database using a Connector, allowing drivers to bypass a
string based data source name.

Most users will open a database via a driver-specific connection helper
function that returns a \*DB. No database drivers are included in the Go
standard library. See https://golang.org/s/sqldrivers> for a list of
third-party drivers.

OpenDB may just validate its arguments without creating a connection to
the database. To verify that the data source name is valid, call Ping.

The returned DB is safe for concurrent use by multiple goroutines and
maintains its own pool of idle connections. Thus, the OpenDB function
should be called just once. It is rarely necessary to close a DB.

### func (\*DB) Begin 

```go
func (db *DB) Begin() (*Tx, error)
```

Begin starts a transaction. The default isolation level is dependent on
the driver.

Begin uses context.Background internally; to specify the context, use
BeginTx.

### func (\*DB) BeginTx 

```go
func (db *DB) BeginTx(ctx context.Context, opts *TxOptions) (*Tx, error)
```

BeginTx starts a transaction.

The provided context is used until the transaction is committed or
rolled back. If the context is canceled, the sql package will roll back
the transaction. Tx.Commit will return an error if the context provided
to BeginTx is canceled.

The provided TxOptions is optional and may be nil if defaults should be
used. If a non-default isolation level is used that the driver doesn\'t
support, an error will be returned.

#### [Example]

Code:

```go
tx, err := db.BeginTx(ctx, &sql.TxOptions{Isolation: sql.LevelSerializable})
if err != nil {
    log.Fatal(err)
}
id := 37
_, execErr := tx.Exec(`UPDATE users SET status = ? WHERE id = ?`, "paid", id)
if execErr != nil {
    _ = tx.Rollback()
    log.Fatal(execErr)
}
if err := tx.Commit(); err != nil {
    log.Fatal(err)
}
```

### func (\*DB) Close 

```go
func (db *DB) Close() error
```

Close closes the database and prevents new queries from starting. Close
then waits for all queries that have started processing on the server to
finish.

It is rare to Close a DB, as the DB handle is meant to be long-lived and
shared between many goroutines.

### func (\*DB) Conn 

```go
func (db *DB) Conn(ctx context.Context) (*Conn, error)
```

Conn returns a single connection by either opening a new connection or
returning an existing connection from the connection pool. Conn will
block until either a connection is returned or ctx is canceled. Queries
run on the same Conn will be run in the same database session.

Every Conn must be returned to the database pool after use by calling
Conn.Close.

### func (\*DB) Driver 

```go
func (db *DB) Driver() driver.Driver
```

Driver returns the database\'s underlying driver.

### func (\*DB) Exec 

```go
func (db *DB) Exec(query string, args ...any) (Result, error)
```

Exec executes a query without returning any rows. The args are for any
placeholder parameters in the query.

Exec uses context.Background internally; to specify the context, use
ExecContext.

### func (\*DB) ExecContext 

```go
func (db *DB) ExecContext(ctx context.Context, query string, args ...any) (Result, error)
```

ExecContext executes a query without returning any rows. The args are
for any placeholder parameters in the query.

#### [Example]

Code:

```go
id := 47
result, err := db.ExecContext(ctx, "UPDATE balances SET balance = balance + 10 WHERE user_id = ?", id)
if err != nil {
    log.Fatal(err)
}
rows, err := result.RowsAffected()
if err != nil {
    log.Fatal(err)
}
if rows != 1 {
    log.Fatalf("expected to affect 1 row, affected %d", rows)
}
```

### func (\*DB) Ping 

```go
func (db *DB) Ping() error
```

Ping verifies a connection to the database is still alive, establishing
a connection if necessary.

Ping uses context.Background internally; to specify the context, use
PingContext.

### func (\*DB) PingContext 

```go
func (db *DB) PingContext(ctx context.Context) error
```

PingContext verifies a connection to the database is still alive,
establishing a connection if necessary.

#### [Example]

Code:

```go
// Ping and PingContext may be used to determine if communication with
// the database server is still possible.
//
// When used in a command line application Ping may be used to establish
// that further queries are possible; that the provided DSN is valid.
//
// When used in long running service Ping may be part of the health
// checking system.

ctx, cancel := context.WithTimeout(ctx, 1*time.Second)
defer cancel()

status := "up"
if err := db.PingContext(ctx); err != nil {
    status = "down"
}
log.Println(status)
```

### func (\*DB) Prepare 

```go
func (db *DB) Prepare(query string) (*Stmt, error)
```

Prepare creates a prepared statement for later queries or executions.
Multiple queries or executions may be run concurrently from the returned
statement. The caller must call the statement\'s Close method when the
statement is no longer needed.

Prepare uses context.Background internally; to specify the context, use
PrepareContext.

#### [Example]

Code:

```go
projects := []struct {
    mascot  string
    release int
}{
    {"tux", 1991},
    {"duke", 1996},
    {"gopher", 2009},
    {"moby dock", 2013},
}

stmt, err := db.Prepare("INSERT INTO projects(id, mascot, release, category) VALUES( ?, ?, ?, ? )")
if err != nil {
    log.Fatal(err)
}
defer stmt.Close() // Prepared statements take up server resources and should be closed after use.

for id, project := range projects {
    if _, err := stmt.Exec(id+1, project.mascot, project.release, "open source"); err != nil {
        log.Fatal(err)
    }
}
```

### func (\*DB) PrepareContext 

```go
func (db *DB) PrepareContext(ctx context.Context, query string) (*Stmt, error)
```

PrepareContext creates a prepared statement for later queries or
executions. Multiple queries or executions may be run concurrently from
the returned statement. The caller must call the statement\'s Close
method when the statement is no longer needed.

The provided context is used for the preparation of the statement, not
for the execution of the statement.

### func (\*DB) Query 

```go
func (db *DB) Query(query string, args ...any) (*Rows, error)
```

Query executes a query that returns rows, typically a SELECT. The args
are for any placeholder parameters in the query.

Query uses context.Background internally; to specify the context, use
QueryContext.

#### [Example (MultipleResultSets)]

Code:

```go
age := 27
q := `
create temp table uid (id bigint); -- Create temp table for queries.
insert into uid
select id from users where age < ?; -- Populate temp table.

-- First result set.
select
    users.id, name
from
    users
    join uid on users.id = uid.id
;

-- Second result set.
select 
    ur.user, ur.role
from
    user_roles as ur
    join uid on uid.id = ur.user
;
    `
rows, err := db.Query(q, age)
if err != nil {
    log.Fatal(err)
}
defer rows.Close()

for rows.Next() {
    var (
        id   int64
        name string
    )
    if err := rows.Scan(&id, &name); err != nil {
        log.Fatal(err)
    }
    log.Printf("id %d name is %s\n", id, name)
}
if !rows.NextResultSet() {
    log.Fatalf("expected more result sets: %v", rows.Err())
}
var roleMap = map[int64]string{
    1: "user",
    2: "admin",
    3: "gopher",
}
for rows.Next() {
    var (
        id   int64
        role int64
    )
    if err := rows.Scan(&id, &role); err != nil {
        log.Fatal(err)
    }
    log.Printf("id %d has role %s\n", id, roleMap[role])
}
if err := rows.Err(); err != nil {
    log.Fatal(err)
}
```

### func (\*DB) QueryContext 

```go
func (db *DB) QueryContext(ctx context.Context, query string, args ...any) (*Rows, error)
```

QueryContext executes a query that returns rows, typically a SELECT. The
args are for any placeholder parameters in the query.

#### [Example]

Code:

```go
age := 27
rows, err := db.QueryContext(ctx, "SELECT name FROM users WHERE age=?", age)
if err != nil {
    log.Fatal(err)
}
defer rows.Close()
names := make([]string, 0)

for rows.Next() {
    var name string
    if err := rows.Scan(&name); err != nil {
        // Check for a scan error.
        // Query rows will be closed with defer.
        log.Fatal(err)
    }
    names = append(names, name)
}
// If the database is being written to ensure to check for Close
// errors that may be returned from the driver. The query may
// encounter an auto-commit error and be forced to rollback changes.
rerr := rows.Close()
if rerr != nil {
    log.Fatal(rerr)
}

// Rows.Err will report the last error encountered by Rows.Scan.
if err := rows.Err(); err != nil {
    log.Fatal(err)
}
fmt.Printf("%s are %d years old", strings.Join(names, ", "), age)
```

### func (\*DB) QueryRow 

```go
func (db *DB) QueryRow(query string, args ...any) *Row
```

QueryRow executes a query that is expected to return at most one row.
QueryRow always returns a non-nil value. Errors are deferred until
Row\'s Scan method is called. If the query selects no rows, the \*Row\'s
Scan will return ErrNoRows. Otherwise, the \*Row\'s Scan scans the first
selected row and discards the rest.

QueryRow uses context.Background internally; to specify the context, use
QueryRowContext.

### func (\*DB) QueryRowContext 

```go
func (db *DB) QueryRowContext(ctx context.Context, query string, args ...any) *Row
```

QueryRowContext executes a query that is expected to return at most one
row. QueryRowContext always returns a non-nil value. Errors are deferred
until Row\'s Scan method is called. If the query selects no rows, the
\*Row\'s Scan will return ErrNoRows. Otherwise, the \*Row\'s Scan scans
the first selected row and discards the rest.

#### [Example]

Code:

```go
id := 123
var username string
var created time.Time
err := db.QueryRowContext(ctx, "SELECT username, created_at FROM users WHERE id=?", id).Scan(&username, &created)
switch {
case err == sql.ErrNoRows:
    log.Printf("no user with id %d\n", id)
case err != nil:
    log.Fatalf("query error: %v\n", err)
default:
    log.Printf("username is %q, account created on %s\n", username, created)
}
```

### func (\*DB) SetConnMaxIdleTime 

```go
func (db *DB) SetConnMaxIdleTime(d time.Duration)
```

SetConnMaxIdleTime sets the maximum amount of time a connection may be
idle.

Expired connections may be closed lazily before reuse.

If d \<= 0, connections are not closed due to a connection\'s idle time.

### func (\*DB) SetConnMaxLifetime 

```go
func (db *DB) SetConnMaxLifetime(d time.Duration)
```

SetConnMaxLifetime sets the maximum amount of time a connection may be
reused.

Expired connections may be closed lazily before reuse.

If d \<= 0, connections are not closed due to a connection\'s age.

### func (\*DB) SetMaxIdleConns 

```go
func (db *DB) SetMaxIdleConns(n int)
```

SetMaxIdleConns sets the maximum number of connections in the idle
connection pool.

If MaxOpenConns is greater than 0 but less than the new MaxIdleConns,
then the new MaxIdleConns will be reduced to match the MaxOpenConns
limit.

If n \<= 0, no idle connections are retained.

The default max idle connections is currently 2. This may change in a
future release.

### func (\*DB) SetMaxOpenConns 

```go
func (db *DB) SetMaxOpenConns(n int)
```

SetMaxOpenConns sets the maximum number of open connections to the
database.

If MaxIdleConns is greater than 0 and the new MaxOpenConns is less than
MaxIdleConns, then MaxIdleConns will be reduced to match the new
MaxOpenConns limit.

If n \<= 0, then there is no limit on the number of open connections.
The default is 0 (unlimited).

### func (\*DB) Stats 

```go
func (db *DB) Stats() DBStats
```

Stats returns database statistics.

type DBStats 
-------------------------------------------

DBStats contains database statistics.

```go
type DBStats struct {
    MaxOpenConnections int // Maximum number of open connections to the database; added in Go 1.11

    // Pool Status
    OpenConnections int // The number of established connections both in use and idle.
    InUse           int // The number of connections currently in use; added in Go 1.11
    Idle            int // The number of idle connections; added in Go 1.11

    // Counters
    WaitCount         int64         // The total number of connections waited for; added in Go 1.11
    WaitDuration      time.Duration // The total time blocked waiting for a new connection; added in Go 1.11
    MaxIdleClosed     int64         // The total number of connections closed due to SetMaxIdleConns; added in Go 1.11
    MaxIdleTimeClosed int64         // The total number of connections closed due to SetConnMaxIdleTime; added in Go 1.15
    MaxLifetimeClosed int64         // The total number of connections closed due to SetConnMaxLifetime; added in Go 1.11
}
```

type IsolationLevel 
--------------------------------------------------

IsolationLevel is the transaction isolation level used in TxOptions.

```go
type IsolationLevel int
```

Various isolation levels that drivers may support in BeginTx. If a
driver does not support a given isolation level an error may be
returned.

See
https://en.wikipedia.org/wiki/Isolation_(database_systems)#Isolation_levels>.

```go
const (
    LevelDefault IsolationLevel = iota
    LevelReadUncommitted
    LevelReadCommitted
    LevelWriteCommitted
    LevelRepeatableRead
    LevelSnapshot
    LevelSerializable
    LevelLinearizable
)
```

### func (IsolationLevel) String 

```go
func (i IsolationLevel) String() string
```

String returns the name of the transaction isolation level.

type NamedArg 
--------------------------------------------

A NamedArg is a named argument. NamedArg values may be used as arguments
to Query or Exec and bind to the corresponding named parameter in the
SQL statement.

For a more concise way to create NamedArg values, see the Named
function.

```go
type NamedArg struct {

    // Name is the name of the parameter placeholder.
    //
    // If empty, the ordinal position in the argument list will be
    // used.
    //
    // Name must omit any symbol prefix.
    Name string

    // Value is the value of the parameter.
    // It may be assigned the same value types as the query
    // arguments.
    Value any
    // contains filtered or unexported fields
}
```

### func Named 

```go
func Named(name string, value any) NamedArg
```

Named provides a more concise way to create NamedArg values.

Example usage:

```go
db.ExecContext(ctx, `
    delete from Invoice
    where
        TimeCreated < @end
        and TimeCreated >= @start;`,
    sql.Named("start", startTime),
    sql.Named("end", endTime),
)
```

type NullBool 
-------------

NullBool represents a bool that may be null. NullBool implements the
Scanner interface so it can be used as a scan destination, similar to
NullString.

```go
type NullBool struct {
    Bool  bool
    Valid bool // Valid is true if Bool is not NULL
}
```

### func (\*NullBool) Scan 

```go
func (n *NullBool) Scan(value any) error
```

Scan implements the Scanner interface.

### func (NullBool) Value 

```go
func (n NullBool) Value() (driver.Value, error)
```

Value implements the driver Valuer interface.

type NullByte 
----------------------------------------------

NullByte represents a byte that may be null. NullByte implements the
Scanner interface so it can be used as a scan destination, similar to
NullString.

```go
type NullByte struct {
    Byte  byte
    Valid bool // Valid is true if Byte is not NULL
}
```

### func (\*NullByte) Scan 

```go
func (n *NullByte) Scan(value any) error
```

Scan implements the Scanner interface.

### func (NullByte) Value 

```go
func (n NullByte) Value() (driver.Value, error)
```

Value implements the driver Valuer interface.

type NullFloat64 
----------------

NullFloat64 represents a float64 that may be null. NullFloat64
implements the Scanner interface so it can be used as a scan
destination, similar to NullString.

```go
type NullFloat64 struct {
    Float64 float64
    Valid   bool // Valid is true if Float64 is not NULL
}
```

### func (\*NullFloat64) Scan 

```go
func (n *NullFloat64) Scan(value any) error
```

Scan implements the Scanner interface.

### func (NullFloat64) Value 

```go
func (n NullFloat64) Value() (driver.Value, error)
```

Value implements the driver Valuer interface.

type NullInt16 
-----------------------------------------------

NullInt16 represents an int16 that may be null. NullInt16 implements the
Scanner interface so it can be used as a scan destination, similar to
NullString.

```go
type NullInt16 struct {
    Int16 int16
    Valid bool // Valid is true if Int16 is not NULL
}
```

### func (\*NullInt16) Scan 

```go
func (n *NullInt16) Scan(value any) error
```

Scan implements the Scanner interface.

### func (NullInt16) Value 

```go
func (n NullInt16) Value() (driver.Value, error)
```

Value implements the driver Valuer interface.

type NullInt32 
-----------------------------------------------

NullInt32 represents an int32 that may be null. NullInt32 implements the
Scanner interface so it can be used as a scan destination, similar to
NullString.

```go
type NullInt32 struct {
    Int32 int32
    Valid bool // Valid is true if Int32 is not NULL
}
```

### func (\*NullInt32) Scan 

```go
func (n *NullInt32) Scan(value any) error
```

Scan implements the Scanner interface.

### func (NullInt32) Value 

```go
func (n NullInt32) Value() (driver.Value, error)
```

Value implements the driver Valuer interface.

type NullInt64 
--------------

NullInt64 represents an int64 that may be null. NullInt64 implements the
Scanner interface so it can be used as a scan destination, similar to
NullString.

```go
type NullInt64 struct {
    Int64 int64
    Valid bool // Valid is true if Int64 is not NULL
}
```

### func (\*NullInt64) Scan 

```go
func (n *NullInt64) Scan(value any) error
```

Scan implements the Scanner interface.

### func (NullInt64) Value 

```go
func (n NullInt64) Value() (driver.Value, error)
```

Value implements the driver Valuer interface.

type NullString 
---------------

NullString represents a string that may be null. NullString implements
the Scanner interface so it can be used as a scan destination:

```go
var s NullString
err := db.QueryRow("SELECT name FROM foo WHERE id=?", id).Scan(&s)
...
if s.Valid {
   // use s.String
} else {
   // NULL value
}
```

```go
type NullString struct {
    String string
    Valid  bool // Valid is true if String is not NULL
}
```

### func (\*NullString) Scan 

```go
func (ns *NullString) Scan(value any) error
```

Scan implements the Scanner interface.

### func (NullString) Value 

```go
func (ns NullString) Value() (driver.Value, error)
```

Value implements the driver Valuer interface.

type NullTime 
----------------------------------------------

NullTime represents a time.Time that may be null. NullTime implements
the Scanner interface so it can be used as a scan destination, similar
to NullString.

```go
type NullTime struct {
    Time  time.Time
    Valid bool // Valid is true if Time is not NULL
}
```

### func (\*NullTime) Scan 

```go
func (n *NullTime) Scan(value any) error
```

Scan implements the Scanner interface.

### func (NullTime) Value 

```go
func (n NullTime) Value() (driver.Value, error)
```

Value implements the driver Valuer interface.

type Out 
---------------------------------------

Out may be used to retrieve OUTPUT value parameters from stored
procedures.

Not all drivers and databases support OUTPUT value parameters.

Example usage:

```go
var outArg string
_, err := db.ExecContext(ctx, "ProcName", sql.Named("Arg1", sql.Out{Dest: &outArg}))
```

```go
type Out struct {

    // Dest is a pointer to the value that will be set to the result of the
    // stored procedure's OUTPUT parameter.
    Dest any

    // In is whether the parameter is an INOUT parameter. If so, the input value to the stored
    // procedure is the dereferenced value of Dest's pointer, which is then replaced with
    // the output value.
    In bool
    // contains filtered or unexported fields
}
```

type RawBytes 
-------------

RawBytes is a byte slice that holds a reference to memory owned by the
database itself. After a Scan into a RawBytes, the slice is only valid
until the next call to Next, Scan, or Close.

```go
type RawBytes []byte
```

type Result 
-----------

A Result summarizes an executed SQL command.

```go
type Result interface {
    // LastInsertId returns the integer generated by the database
    // in response to a command. Typically this will be from an
    // "auto increment" column when inserting a new row. Not all
    // databases support this feature, and the syntax of such
    // statements varies.
    LastInsertId() (int64, error)

    // RowsAffected returns the number of rows affected by an
    // update, insert, or delete. Not every database or database
    // driver may support this.
    RowsAffected() (int64, error)
}
```

type Row 
--------

Row is the result of calling QueryRow to select a single row.

```go
type Row struct {
    // contains filtered or unexported fields
}
```

### func (\*Row) Err 

```go
func (r *Row) Err() error
```

Err provides a way for wrapping packages to check for query errors
without calling Scan. Err returns the error, if any, that was
encountered while running the query. If this error is not nil, this
error will also be returned from Scan.

### func (\*Row) Scan 

```go
func (r *Row) Scan(dest ...any) error
```

Scan copies the columns from the matched row into the values pointed at
by dest. See the documentation on Rows.Scan for details. If more than
one row matches the query, Scan uses the first row and discards the
rest. If no row matches the query, Scan returns ErrNoRows.

type Rows 
---------

Rows is the result of a query. Its cursor starts before the first row of
the result set. Use Next to advance from row to row.

```go
type Rows struct {
    // contains filtered or unexported fields
}
```

#### [Example]

Code:

```go
age := 27
rows, err := db.QueryContext(ctx, "SELECT name FROM users WHERE age=?", age)
if err != nil {
    log.Fatal(err)
}
defer rows.Close()

names := make([]string, 0)
for rows.Next() {
    var name string
    if err := rows.Scan(&name); err != nil {
        log.Fatal(err)
    }
    names = append(names, name)
}
// Check for errors from iterating over rows.
if err := rows.Err(); err != nil {
    log.Fatal(err)
}
log.Printf("%s are %d years old", strings.Join(names, ", "), age)
```

### func (\*Rows) Close 

```go
func (rs *Rows) Close() error
```

Close closes the Rows, preventing further enumeration. If Next is called
and returns false and there are no further result sets, the Rows are
closed automatically and it will suffice to check the result of Err.
Close is idempotent and does not affect the result of Err.

### func (\*Rows) ColumnTypes 

```go
func (rs *Rows) ColumnTypes() ([]*ColumnType, error)
```

ColumnTypes returns column information such as column type, length, and
nullable. Some information may not be available from some drivers.

### func (\*Rows) Columns 

```go
func (rs *Rows) Columns() ([]string, error)
```

Columns returns the column names. Columns returns an error if the rows
are closed.

### func (\*Rows) Err 

```go
func (rs *Rows) Err() error
```

Err returns the error, if any, that was encountered during iteration.
Err may be called after an explicit or implicit Close.

### func (\*Rows) Next 

```go
func (rs *Rows) Next() bool
```

Next prepares the next result row for reading with the Scan method. It
returns true on success, or false if there is no next result row or an
error happened while preparing it. Err should be consulted to
distinguish between the two cases.

Every call to Scan, even the first one, must be preceded by a call to
Next.

### func (\*Rows) NextResultSet 

```go
func (rs *Rows) NextResultSet() bool
```

NextResultSet prepares the next result set for reading. It reports
whether there is further result sets, or false if there is no further
result set or if there is an error advancing to it. The Err method
should be consulted to distinguish between the two cases.

After calling NextResultSet, the Next method should always be called
before scanning. If there are further result sets they may not have rows
in the result set.

### func (\*Rows) Scan 

```go
func (rs *Rows) Scan(dest ...any) error
```

Scan copies the columns in the current row into the values pointed at by
dest. The number of values in dest must be the same as the number of
columns in Rows.

Scan converts columns read from the database into the following common
Go types and special types provided by the sql package:

```go
*string
*[]byte
*int, *int8, *int16, *int32, *int64
*uint, *uint8, *uint16, *uint32, *uint64
*bool
*float32, *float64
*interface{}
*RawBytes
*Rows (cursor value)
any type implementing Scanner (see Scanner docs)
```

In the most simple case, if the type of the value from the source column
is an integer, bool or string type T and dest is of type \*T, Scan
simply assigns the value through the pointer.

Scan also converts between string and numeric types, as long as no
information would be lost. While Scan stringifies all numbers scanned
from numeric database columns into \*string, scans into numeric types
are checked for overflow. For example, a float64 with value 300 or a
string with value \"300\" can scan into a uint16, but not into a uint8,
though float64(255) or \"255\" can scan into a uint8. One exception is
that scans of some float64 numbers to strings may lose information when
stringifying. In general, scan floating point columns into \*float64.

If a dest argument has type \*\[\]byte, Scan saves in that argument a
copy of the corresponding data. The copy is owned by the caller and can
be modified and held indefinitely. The copy can be avoided by using an
argument of type \*RawBytes instead; see the documentation for RawBytes
for restrictions on its use.

If an argument has type \*interface{}, Scan copies the value provided by
the underlying driver without conversion. When scanning from a source
value of type \[\]byte to \*interface{}, a copy of the slice is made and
the caller owns the result.

Source values of type time.Time may be scanned into values of type
\*time.Time, \*interface{}, \*string, or \*\[\]byte. When converting to
the latter two, time.RFC3339Nano is used.

Source values of type bool may be scanned into types \*bool,
\*interface{}, \*string, \*\[\]byte, or \*RawBytes.

For scanning into \*bool, the source may be true, false, 1, 0, or string
inputs parseable by strconv.ParseBool.

Scan can also convert a cursor returned from a query, such as \"select
cursor(select \* from my\_table) from dual\", into a \*Rows value that
can itself be scanned from. The parent select query will close any
cursor \*Rows if the parent \*Rows is closed.

If any of the first arguments implementing Scanner returns an error,
that error will be wrapped in the returned error.

type Scanner 
------------

Scanner is an interface used by Scan.

```go
type Scanner interface {
    // Scan assigns a value from a database driver.
    //
    // The src value will be of one of the following types:
    //
    //    int64
    //    float64
    //    bool
    //    []byte
    //    string
    //    time.Time
    //    nil - for NULL values
    //
    // An error should be returned if the value cannot be stored
    // without loss of information.
    //
    // Reference types such as []byte are only valid until the next call to Scan
    // and should not be retained. Their underlying memory is owned by the driver.
    // If retention is necessary, copy their values before the next call to Scan.
    Scan(src any) error
}
```

type Stmt 
---------

Stmt is a prepared statement. A Stmt is safe for concurrent use by
multiple goroutines.

If a Stmt is prepared on a Tx or Conn, it will be bound to a single
underlying connection forever. If the Tx or Conn closes, the Stmt will
become unusable and all operations will return an error. If a Stmt is
prepared on a DB, it will remain usable for the lifetime of the DB. When
the Stmt needs to execute on a new underlying connection, it will
prepare itself on the new connection automatically.

```go
type Stmt struct {
    // contains filtered or unexported fields
}
```

#### [Example]

Code:

```go
// In normal use, create one Stmt when your process starts.
stmt, err := db.PrepareContext(ctx, "SELECT username FROM users WHERE id = ?")
if err != nil {
    log.Fatal(err)
}
defer stmt.Close()

// Then reuse it each time you need to issue the query.
id := 43
var username string
err = stmt.QueryRowContext(ctx, id).Scan(&username)
switch {
case err == sql.ErrNoRows:
    log.Fatalf("no user with id %d", id)
case err != nil:
    log.Fatal(err)
default:
    log.Printf("username is %s\n", username)
}
```

### func (\*Stmt) Close 

```go
func (s *Stmt) Close() error
```

Close closes the statement.

### func (\*Stmt) Exec 

```go
func (s *Stmt) Exec(args ...any) (Result, error)
```

Exec executes a prepared statement with the given arguments and returns
a Result summarizing the effect of the statement.

Exec uses context.Background internally; to specify the context, use
ExecContext.

### func (\*Stmt) ExecContext 

```go
func (s *Stmt) ExecContext(ctx context.Context, args ...any) (Result, error)
```

ExecContext executes a prepared statement with the given arguments and
returns a Result summarizing the effect of the statement.

### func (\*Stmt) Query 

```go
func (s *Stmt) Query(args ...any) (*Rows, error)
```

Query executes a prepared query statement with the given arguments and
returns the query results as a \*Rows.

Query uses context.Background internally; to specify the context, use
QueryContext.

### func (\*Stmt) QueryContext 

```go
func (s *Stmt) QueryContext(ctx context.Context, args ...any) (*Rows, error)
```

QueryContext executes a prepared query statement with the given
arguments and returns the query results as a \*Rows.

### func (\*Stmt) QueryRow 

```go
func (s *Stmt) QueryRow(args ...any) *Row
```

QueryRow executes a prepared query statement with the given arguments.
If an error occurs during the execution of the statement, that error
will be returned by a call to Scan on the returned \*Row, which is
always non-nil. If the query selects no rows, the \*Row\'s Scan will
return ErrNoRows. Otherwise, the \*Row\'s Scan scans the first selected
row and discards the rest.

Example usage:

```go
var name string
err := nameByUseridStmt.QueryRow(id).Scan(&name)
```

QueryRow uses context.Background internally; to specify the context, use
QueryRowContext.

### func (\*Stmt) QueryRowContext 

```go
func (s *Stmt) QueryRowContext(ctx context.Context, args ...any) *Row
```

QueryRowContext executes a prepared query statement with the given
arguments. If an error occurs during the execution of the statement,
that error will be returned by a call to Scan on the returned \*Row,
which is always non-nil. If the query selects no rows, the \*Row\'s Scan
will return ErrNoRows. Otherwise, the \*Row\'s Scan scans the first
selected row and discards the rest.

#### [Example]

Code:

```go
// In normal use, create one Stmt when your process starts.
stmt, err := db.PrepareContext(ctx, "SELECT username FROM users WHERE id = ?")
if err != nil {
    log.Fatal(err)
}
defer stmt.Close()

// Then reuse it each time you need to issue the query.
id := 43
var username string
err = stmt.QueryRowContext(ctx, id).Scan(&username)
switch {
case err == sql.ErrNoRows:
    log.Fatalf("no user with id %d", id)
case err != nil:
    log.Fatal(err)
default:
    log.Printf("username is %s\n", username)
}
```

type Tx 
-------

Tx is an in-progress database transaction.

A transaction must end with a call to Commit or Rollback.

After a call to Commit or Rollback, all operations on the transaction
fail with ErrTxDone.

The statements prepared for a transaction by calling the transaction\'s
Prepare or Stmt methods are closed by the call to Commit or Rollback.

```go
type Tx struct {
    // contains filtered or unexported fields
}
```

### func (\*Tx) Commit 

```go
func (tx *Tx) Commit() error
```

Commit commits the transaction.

### func (\*Tx) Exec 

```go
func (tx *Tx) Exec(query string, args ...any) (Result, error)
```

Exec executes a query that doesn\'t return rows. For example: an INSERT
and UPDATE.

Exec uses context.Background internally; to specify the context, use
ExecContext.

### func (\*Tx) ExecContext 

```go
func (tx *Tx) ExecContext(ctx context.Context, query string, args ...any) (Result, error)
```

ExecContext executes a query that doesn\'t return rows. For example: an
INSERT and UPDATE.

#### [Example]

Code:

```go
tx, err := db.BeginTx(ctx, &sql.TxOptions{Isolation: sql.LevelSerializable})
if err != nil {
    log.Fatal(err)
}
id := 37
_, execErr := tx.ExecContext(ctx, "UPDATE users SET status = ? WHERE id = ?", "paid", id)
if execErr != nil {
    if rollbackErr := tx.Rollback(); rollbackErr != nil {
        log.Fatalf("update failed: %v, unable to rollback: %v\n", execErr, rollbackErr)
    }
    log.Fatalf("update failed: %v", execErr)
}
if err := tx.Commit(); err != nil {
    log.Fatal(err)
}
```

### func (\*Tx) Prepare 

```go
func (tx *Tx) Prepare(query string) (*Stmt, error)
```

Prepare creates a prepared statement for use within a transaction.

The returned statement operates within the transaction and will be
closed when the transaction has been committed or rolled back.

To use an existing prepared statement on this transaction, see Tx.Stmt.

Prepare uses context.Background internally; to specify the context, use
PrepareContext.

#### [Example]

Code:

```go
projects := []struct {
    mascot  string
    release int
}{
    {"tux", 1991},
    {"duke", 1996},
    {"gopher", 2009},
    {"moby dock", 2013},
}

tx, err := db.Begin()
if err != nil {
    log.Fatal(err)
}
defer tx.Rollback() // The rollback will be ignored if the tx has been committed later in the function.

stmt, err := tx.Prepare("INSERT INTO projects(id, mascot, release, category) VALUES( ?, ?, ?, ? )")
if err != nil {
    log.Fatal(err)
}
defer stmt.Close() // Prepared statements take up server resources and should be closed after use.

for id, project := range projects {
    if _, err := stmt.Exec(id+1, project.mascot, project.release, "open source"); err != nil {
        log.Fatal(err)
    }
}
if err := tx.Commit(); err != nil {
    log.Fatal(err)
}
```

### func (\*Tx) PrepareContext 

```go
func (tx *Tx) PrepareContext(ctx context.Context, query string) (*Stmt, error)
```

PrepareContext creates a prepared statement for use within a
transaction.

The returned statement operates within the transaction and will be
closed when the transaction has been committed or rolled back.

To use an existing prepared statement on this transaction, see Tx.Stmt.

The provided context will be used for the preparation of the context,
not for the execution of the returned statement. The returned statement
will run in the transaction context.

### func (\*Tx) Query 

```go
func (tx *Tx) Query(query string, args ...any) (*Rows, error)
```

Query executes a query that returns rows, typically a SELECT.

Query uses context.Background internally; to specify the context, use
QueryContext.

### func (\*Tx) QueryContext 

```go
func (tx *Tx) QueryContext(ctx context.Context, query string, args ...any) (*Rows, error)
```

QueryContext executes a query that returns rows, typically a SELECT.

### func (\*Tx) QueryRow 

```go
func (tx *Tx) QueryRow(query string, args ...any) *Row
```

QueryRow executes a query that is expected to return at most one row.
QueryRow always returns a non-nil value. Errors are deferred until
Row\'s Scan method is called. If the query selects no rows, the \*Row\'s
Scan will return ErrNoRows. Otherwise, the \*Row\'s Scan scans the first
selected row and discards the rest.

QueryRow uses context.Background internally; to specify the context, use
QueryRowContext.

### func (\*Tx) QueryRowContext 

```go
func (tx *Tx) QueryRowContext(ctx context.Context, query string, args ...any) *Row
```

QueryRowContext executes a query that is expected to return at most one
row. QueryRowContext always returns a non-nil value. Errors are deferred
until Row\'s Scan method is called. If the query selects no rows, the
\*Row\'s Scan will return ErrNoRows. Otherwise, the \*Row\'s Scan scans
the first selected row and discards the rest.

### func (\*Tx) Rollback 

```go
func (tx *Tx) Rollback() error
```

Rollback aborts the transaction.

#### [Example]

Code:

```go
tx, err := db.BeginTx(ctx, &sql.TxOptions{Isolation: sql.LevelSerializable})
if err != nil {
    log.Fatal(err)
}
id := 53
_, err = tx.ExecContext(ctx, "UPDATE drivers SET status = ? WHERE id = ?;", "assigned", id)
if err != nil {
    if rollbackErr := tx.Rollback(); rollbackErr != nil {
        log.Fatalf("update drivers: unable to rollback: %v", rollbackErr)
    }
    log.Fatal(err)
}
_, err = tx.ExecContext(ctx, "UPDATE pickups SET driver_id = $1;", id)
if err != nil {
    if rollbackErr := tx.Rollback(); rollbackErr != nil {
        log.Fatalf("update failed: %v, unable to back: %v", err, rollbackErr)
    }
    log.Fatal(err)
}
if err := tx.Commit(); err != nil {
    log.Fatal(err)
}
```

### func (\*Tx) Stmt 

```go
func (tx *Tx) Stmt(stmt *Stmt) *Stmt
```

Stmt returns a transaction-specific prepared statement from an existing
statement.

Example:

```go
updateMoney, err := db.Prepare("UPDATE balance SET money=money+? WHERE id=?")
...
tx, err := db.Begin()
...
res, err := tx.Stmt(updateMoney).Exec(123.45, 98293203)
```

The returned statement operates within the transaction and will be
closed when the transaction has been committed or rolled back.

Stmt uses context.Background internally; to specify the context, use
StmtContext.

### func (\*Tx) StmtContext 

```go
func (tx *Tx) StmtContext(ctx context.Context, stmt *Stmt) *Stmt
```

StmtContext returns a transaction-specific prepared statement from an
existing statement.

Example:

```go
updateMoney, err := db.Prepare("UPDATE balance SET money=money+? WHERE id=?")
...
tx, err := db.Begin()
...
res, err := tx.StmtContext(ctx, updateMoney).Exec(123.45, 98293203)
```

The provided context is used for the preparation of the statement, not
for the execution of the statement.

The returned statement operates within the transaction and will be
closed when the transaction has been committed or rolled back.

type TxOptions 
---------------------------------------------

TxOptions holds the transaction options to be used in DB.BeginTx.

```go
type TxOptions struct {
    // Isolation is the transaction isolation level.
    // If zero, the driver or database's default level is used.
    Isolation IsolationLevel
    ReadOnly  bool
}
```

Subdirectories 
--------------

 
Name


Synopsis

[..](../index)

[driver](driver/index)

Package driver defines interfaces to be implemented by database drivers
as used by package sql.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/database/sql/>

