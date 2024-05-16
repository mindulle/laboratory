Package iotest
==============

-   `import "testing/iotest"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package iotest implements Readers and Writers useful mainly for testing.

Index 
-----

-   [Variables](#pkg-variables)
-   [func DataErrReader(r io.Reader) io.Reader](#DataErrReader)
-   [func ErrReader(err error) io.Reader](#ErrReader)
-   [func HalfReader(r io.Reader) io.Reader](#HalfReader)
-   [func NewReadLogger(prefix string, r io.Reader)
    io.Reader](#NewReadLogger)
-   [func NewWriteLogger(prefix string, w io.Writer)
    io.Writer](#NewWriteLogger)
-   [func OneByteReader(r io.Reader) io.Reader](#OneByteReader)
-   [func TestReader(r io.Reader, content \[\]byte) error](#TestReader)
-   [func TimeoutReader(r io.Reader) io.Reader](#TimeoutReader)
-   [func TruncateWriter(w io.Writer, n int64)
    io.Writer](#TruncateWriter)

 
### Examples

[ErrReader](#example_ErrReader)


### Package files

logger.go reader.go writer.go

Variables 
---------

ErrTimeout is a fake timeout error.

```go
var ErrTimeout = errors.New("timeout")
```

func DataErrReader 
------------------

```go
func DataErrReader(r io.Reader) io.Reader
```

DataErrReader changes the way errors are handled by a Reader. Normally,
a Reader returns an error (typically EOF) from the first Read call after
the last piece of data is read. DataErrReader wraps a Reader and changes
its behavior so the final error is returned along with the final data,
instead of in the first call after the final data.

func ErrReader 
-----------------------------------------------

```go
func ErrReader(err error) io.Reader
```

ErrReader returns an io.Reader that returns 0, err from all Read calls.

#### [Example]

Code:

```go
// A reader that always returns a custom error.
r := iotest.ErrReader(errors.New("custom error"))
n, err := r.Read(nil)
fmt.Printf("n:   %d\nerr: %q\n", n, err)
```

Output:

```go
n:   0
err: "custom error"
```

func HalfReader 
---------------

```go
func HalfReader(r io.Reader) io.Reader
```

HalfReader returns a Reader that implements Read by reading half as many
requested bytes from r.

func NewReadLogger 
------------------

```go
func NewReadLogger(prefix string, r io.Reader) io.Reader
```

NewReadLogger returns a reader that behaves like r except that it logs
(using log.Printf) each read to standard error, printing the prefix and
the hexadecimal data read.

func NewWriteLogger 
-------------------

```go
func NewWriteLogger(prefix string, w io.Writer) io.Writer
```

NewWriteLogger returns a writer that behaves like w except that it logs
(using log.Printf) each write to standard error, printing the prefix and
the hexadecimal data written.

func OneByteReader 
------------------

```go
func OneByteReader(r io.Reader) io.Reader
```

OneByteReader returns a Reader that implements each non-empty Read by
reading one byte from r.

func TestReader 
------------------------------------------------

```go
func TestReader(r io.Reader, content []byte) error
```

TestReader tests that reading from r returns the expected file content.
It does reads of different sizes, until EOF. If r implements io.ReaderAt
or io.Seeker, TestReader also checks that those operations behave as
they should.

If TestReader finds any misbehaviors, it returns an error reporting
them. The error text may span multiple lines.

func TimeoutReader 
------------------

```go
func TimeoutReader(r io.Reader) io.Reader
```

TimeoutReader returns ErrTimeout on the second read with no data.
Subsequent calls to read succeed.

func TruncateWriter 
-------------------

```go
func TruncateWriter(w io.Writer, n int64) io.Writer
```

TruncateWriter returns a Writer that writes to w but stops silently
after n bytes.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/testing/iotest/>

