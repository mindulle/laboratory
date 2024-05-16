Package internal
================

-   `import "net/http/internal"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Subdirectories](#pkg-subdirectories)

Overview 
--------

Package internal contains HTTP internals shared by net/http and
net/http/httputil.

Index 
-----

-   [Variables](#pkg-variables)
-   [func NewChunkedReader(r io.Reader) io.Reader](#NewChunkedReader)
-   [func NewChunkedWriter(w io.Writer)
    io.WriteCloser](#NewChunkedWriter)
-   [type FlushAfterChunkWriter](#FlushAfterChunkWriter)

### Package files

chunked.go

Variables 
---------

```go
var ErrLineTooLong = errors.New("header line too long")
```

func NewChunkedReader 
---------------------

```go
func NewChunkedReader(r io.Reader) io.Reader
```

NewChunkedReader returns a new chunkedReader that translates the data
read from r out of HTTP \"chunked\" format before returning it. The
chunkedReader returns io.EOF when the final 0-length chunk is read.

NewChunkedReader is not needed by normal applications. The http package
automatically decodes chunking when reading response bodies.

func NewChunkedWriter 
---------------------

```go
func NewChunkedWriter(w io.Writer) io.WriteCloser
```

NewChunkedWriter returns a new chunkedWriter that translates writes into
HTTP \"chunked\" format before writing them to w. Closing the returned
chunkedWriter sends the final 0-length chunk that marks the end of the
stream but does not send the final CRLF that appears after trailers;
trailers and the last CRLF must be written separately.

NewChunkedWriter is not needed by normal applications. The http package
adds chunking automatically if handlers don\'t set a Content-Length
header. Using newChunkedWriter inside a handler would result in double
chunking or chunking with a Content-Length length, both of which are
wrong.

type FlushAfterChunkWriter 
--------------------------

FlushAfterChunkWriter signals from the caller of NewChunkedWriter that
each chunk should be followed by a flush. It is used by the
http.Transport code to keep the buffering behavior for headers and
trailers, but flush out chunks aggressively in the middle for request
bodies which may be generated slowly. See Issue 6574.

```go
type FlushAfterChunkWriter struct {
    *bufio.Writer
}
```

Subdirectories 
--------------

 
Name


Synopsis

[..](../index)

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/net/http/internal/>

