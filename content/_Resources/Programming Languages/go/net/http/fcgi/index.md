Package fcgi
============

-   `import "net/http/fcgi"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package fcgi implements the FastCGI protocol.

See https://fast-cgi.github.io/> for an unofficial mirror of the
original documentation.

Currently only the responder role is supported.

Index 
-----

-   [Variables](#pkg-variables)
-   [func ProcessEnv(r \*http.Request) map\[string\]string](#ProcessEnv)
-   [func Serve(l net.Listener, handler http.Handler) error](#Serve)

### Package files

child.go fcgi.go

Variables 
---------

ErrConnClosed is returned by Read when a handler attempts to read the
body of a request after the connection to the web server has been
closed.

```go
var ErrConnClosed = errors.New("fcgi: connection to web server closed")
```

ErrRequestAborted is returned by Read when a handler attempts to read
the body of a request that has been aborted by the web server.

```go
var ErrRequestAborted = errors.New("fcgi: request aborted by web server")
```

func ProcessEnv 
----------------------------------------------

```go
func ProcessEnv(r *http.Request) map[string]string
```

ProcessEnv returns FastCGI environment variables associated with the
request r for which no effort was made to be included in the request
itself - the data is hidden in the request\'s context. As an example, if
REMOTE\_USER is set for a request, it will not be found anywhere in r,
but it will be included in ProcessEnv\'s response (via r\'s context).

func Serve 
----------

```go
func Serve(l net.Listener, handler http.Handler) error
```

Serve accepts incoming FastCGI connections on the listener l, creating a
new goroutine for each. The goroutine reads requests and then calls
handler to reply to them. If l is nil, Serve accepts connections from
os.Stdin. If handler is nil, http.DefaultServeMux is used.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/net/http/fcgi/>

