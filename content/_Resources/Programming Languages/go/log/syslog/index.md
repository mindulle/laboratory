Package syslog
==============

- `import "log/syslog"`
- [Overview](#pkg-overview)
- [Index](#pkg-index)
- [Examples](#pkg-examples)

Overview
--------

Package syslog provides a simple interface to the system log service. It
can send messages to the syslog daemon using UNIX domain sockets, UDP or
TCP.

Only one call to Dial is necessary. On write failures, the syslog client
will attempt to reconnect to the server and write again.

The syslog package is frozen and is not accepting new features. Some
external packages provide more functionality. See:

```go
https://godoc.org/?q=syslog
```

Index
-----

- [func NewLogger(p Priority, logFlag int) (\*log.Logger,
    error)](#NewLogger)
- [type Priority](#Priority)
- [type Writer](#Writer)
- [func Dial(network, raddr string, priority Priority, tag string)
    (\*Writer, error)](#Dial)
- [func New(priority Priority, tag string) (\*Writer, error)](#New)
- [func (w \*Writer) Alert(m string) error](#Writer.Alert)
- [func (w \*Writer) Close() error](#Writer.Close)
- [func (w \*Writer) Crit(m string) error](#Writer.Crit)
- [func (w \*Writer) Debug(m string) error](#Writer.Debug)
- [func (w \*Writer) Emerg(m string) error](#Writer.Emerg)
- [func (w \*Writer) Err(m string) error](#Writer.Err)
- [func (w \*Writer) Info(m string) error](#Writer.Info)
- [func (w \*Writer) Notice(m string) error](#Writer.Notice)
- [func (w \*Writer) Warning(m string) error](#Writer.Warning)
- [func (w \*Writer) Write(b \[\]byte) (int, error)](#Writer.Write)
- [Bugs](#pkg-note-BUG)

### Examples

[Dial](#example_Dial)

### Package files

doc.go syslog.go syslog\_unix.go

func NewLogger
--------------

```go
func NewLogger(p Priority, logFlag int) (*log.Logger, error)
```

NewLogger creates a log.Logger whose output is written to the system log
service with the specified priority, a combination of the syslog
facility and severity. The logFlag argument is the flag set passed
through to log.New to create the Logger.

type Priority
-------------

The Priority is a combination of the syslog facility and severity. For
example, LOG\_ALERT \| LOG\_FTP sends an alert severity message from the
FTP facility. The default severity is LOG\_EMERG; the default facility
is LOG\_KERN.

```go
type Priority int
```

```go
const (

    // From /usr/include/sys/syslog.h.
    // These are the same on Linux, BSD, and OS X.
    LOG_EMERG Priority = iota
    LOG_ALERT
    LOG_CRIT
    LOG_ERR
    LOG_WARNING
    LOG_NOTICE
    LOG_INFO
    LOG_DEBUG
)
```

```go
const (

    // From /usr/include/sys/syslog.h.
    // These are the same up to LOG_FTP on Linux, BSD, and OS X.
    LOG_KERN Priority = iota << 3
    LOG_USER
    LOG_MAIL
    LOG_DAEMON
    LOG_AUTH
    LOG_SYSLOG
    LOG_LPR
    LOG_NEWS
    LOG_UUCP
    LOG_CRON
    LOG_AUTHPRIV
    LOG_FTP

    LOG_LOCAL0
    LOG_LOCAL1
    LOG_LOCAL2
    LOG_LOCAL3
    LOG_LOCAL4
    LOG_LOCAL5
    LOG_LOCAL6
    LOG_LOCAL7
)
```

type Writer
-----------

A Writer is a connection to a syslog server.

```go
type Writer struct {
    // contains filtered or unexported fields
}
```

### func Dial

```go
func Dial(network, raddr string, priority Priority, tag string) (*Writer, error)
```

Dial establishes a connection to a log daemon by connecting to address
raddr on the specified network. Each write to the returned writer sends
a log message with the facility and severity (from priority) and tag. If
tag is empty, the os.Args\[0\] is used. If network is empty, Dial will
connect to the local syslog server. Otherwise, see the documentation for
net.Dial for valid values of network and raddr.

#### [Example]

Code:

```go
sysLog, err := syslog.Dial("tcp", "localhost:1234",
    syslog.LOG_WARNING|syslog.LOG_DAEMON, "demotag")
if err != nil {
    log.Fatal(err)
}
fmt.Fprintf(sysLog, "This is a daemon warning with demotag.")
sysLog.Emerg("And this is a daemon emergency with demotag.")
```

### func New

```go
func New(priority Priority, tag string) (*Writer, error)
```

New establishes a new connection to the system log daemon. Each write to
the returned writer sends a log message with the given priority (a
combination of the syslog facility and severity) and prefix tag. If tag
is empty, the os.Args\[0\] is used.

### func (\*Writer) Alert

```go
func (w *Writer) Alert(m string) error
```

Alert logs a message with severity LOG\_ALERT, ignoring the severity
passed to New.

### func (\*Writer) Close

```go
func (w *Writer) Close() error
```

Close closes a connection to the syslog daemon.

### func (\*Writer) Crit

```go
func (w *Writer) Crit(m string) error
```

Crit logs a message with severity LOG\_CRIT, ignoring the severity
passed to New.

### func (\*Writer) Debug

```go
func (w *Writer) Debug(m string) error
```

Debug logs a message with severity LOG\_DEBUG, ignoring the severity
passed to New.

### func (\*Writer) Emerg

```go
func (w *Writer) Emerg(m string) error
```

Emerg logs a message with severity LOG\_EMERG, ignoring the severity
passed to New.

### func (\*Writer) Err

```go
func (w *Writer) Err(m string) error
```

Err logs a message with severity LOG\_ERR, ignoring the severity passed
to New.

### func (\*Writer) Info

```go
func (w *Writer) Info(m string) error
```

Info logs a message with severity LOG\_INFO, ignoring the severity
passed to New.

### func (\*Writer) Notice

```go
func (w *Writer) Notice(m string) error
```

Notice logs a message with severity LOG\_NOTICE, ignoring the severity
passed to New.

### func (\*Writer) Warning

```go
func (w *Writer) Warning(m string) error
```

Warning logs a message with severity LOG\_WARNING, ignoring the severity
passed to New.

### func (\*Writer) Write

```go
func (w *Writer) Write(b []byte) (int, error)
```

Write sends a log message to the syslog daemon.

Bugs
----

-

    This package is not implemented on Windows. As the syslog package is
    frozen, Windows users are encouraged to use a package outside of the
    standard library. For background, see
    https://golang.org/issue/1108>.

-

    This package is not implemented on Plan 9.

© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/log/syslog/>
