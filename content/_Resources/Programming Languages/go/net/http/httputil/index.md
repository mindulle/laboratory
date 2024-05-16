Package httputil
================

-   `import "net/http/httputil"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package httputil provides HTTP utility functions, complementing the more
common ones in the net/http package.

Index 
-----

-   [Variables](#pkg-variables)
-   [func DumpRequest(req \*http.Request, body bool) (\[\]byte,
    error)](#DumpRequest)
-   [func DumpRequestOut(req \*http.Request, body bool) (\[\]byte,
    error)](#DumpRequestOut)
-   [func DumpResponse(resp \*http.Response, body bool) (\[\]byte,
    error)](#DumpResponse)
-   [func NewChunkedReader(r io.Reader) io.Reader](#NewChunkedReader)
-   [func NewChunkedWriter(w io.Writer)
    io.WriteCloser](#NewChunkedWriter)
-   [type BufferPool](#BufferPool)
-   [type ClientConn](#ClientConn)
-   [func NewClientConn(c net.Conn, r \*bufio.Reader)
    \*ClientConn](#NewClientConn)
-   [func NewProxyClientConn(c net.Conn, r \*bufio.Reader)
    \*ClientConn](#NewProxyClientConn)
-   [func (cc \*ClientConn) Close() error](#ClientConn.Close)
-   [func (cc \*ClientConn) Do(req \*http.Request) (\*http.Response,
    error)](#ClientConn.Do)
-   [func (cc \*ClientConn) Hijack() (c net.Conn, r
    \*bufio.Reader)](#ClientConn.Hijack)
-   [func (cc \*ClientConn) Pending() int](#ClientConn.Pending)
-   [func (cc \*ClientConn) Read(req \*http.Request) (resp
    \*http.Response, err error)](#ClientConn.Read)
-   [func (cc \*ClientConn) Write(req \*http.Request)
    error](#ClientConn.Write)
-   [type ProxyRequest](#ProxyRequest)
-   [func (r \*ProxyRequest) SetURL(target
    \*url.URL)](#ProxyRequest.SetURL)
-   [func (r \*ProxyRequest)
    SetXForwarded()](#ProxyRequest.SetXForwarded)
-   [type ReverseProxy](#ReverseProxy)
-   [func NewSingleHostReverseProxy(target \*url.URL)
    \*ReverseProxy](#NewSingleHostReverseProxy)
-   [func (p \*ReverseProxy) ServeHTTP(rw http.ResponseWriter, req
    \*http.Request)](#ReverseProxy.ServeHTTP)
-   [type ServerConn](#ServerConn)
-   [func NewServerConn(c net.Conn, r \*bufio.Reader)
    \*ServerConn](#NewServerConn)
-   [func (sc \*ServerConn) Close() error](#ServerConn.Close)
-   [func (sc \*ServerConn) Hijack() (net.Conn,
    \*bufio.Reader)](#ServerConn.Hijack)
-   [func (sc \*ServerConn) Pending() int](#ServerConn.Pending)
-   [func (sc \*ServerConn) Read() (\*http.Request,
    error)](#ServerConn.Read)
-   [func (sc \*ServerConn) Write(req \*http.Request, resp
    \*http.Response) error](#ServerConn.Write)

 
### Examples

[DumpRequest](#example_DumpRequest)

[DumpRequestOut](#example_DumpRequestOut)

[DumpResponse](#example_DumpResponse)

[ReverseProxy](#example_ReverseProxy)


### Package files

dump.go httputil.go persist.go reverseproxy.go

Variables 
---------

```go
var (
    // Deprecated: No longer used.
    ErrPersistEOF = &http.ProtocolError{ErrorString: "persistent connection closed"}

    // Deprecated: No longer used.
    ErrClosed = &http.ProtocolError{ErrorString: "connection closed by user"}

    // Deprecated: No longer used.
    ErrPipeline = &http.ProtocolError{ErrorString: "pipeline error"}
)
```

ErrLineTooLong is returned when reading malformed chunked data with
lines that are too long.

```go
var ErrLineTooLong = internal.ErrLineTooLong
```

func DumpRequest 
----------------

```go
func DumpRequest(req *http.Request, body bool) ([]byte, error)
```

DumpRequest returns the given request in its HTTP/1.x wire
representation. It should only be used by servers to debug client
requests. The returned representation is an approximation only; some
details of the initial request are lost while parsing it into an
http.Request. In particular, the order and case of header field names
are lost. The order of values in multi-valued headers is kept intact.
HTTP/2 requests are dumped in HTTP/1.x form, not in their original
binary representations.

If body is true, DumpRequest also returns the body. To do so, it
consumes req.Body and then replaces it with a new io.ReadCloser that
yields the same bytes. If DumpRequest returns an error, the state of req
is undefined.

The documentation for http.Request.Write details which fields of req are
included in the dump.

#### [Example]

Code:

```go
ts := httptest.NewServer(http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
    dump, err := httputil.DumpRequest(r, true)
    if err != nil {
        http.Error(w, fmt.Sprint(err), http.StatusInternalServerError)
        return
    }

    fmt.Fprintf(w, "%q", dump)
}))
defer ts.Close()

const body = "Go is a general-purpose language designed with systems programming in mind."
req, err := http.NewRequest("POST", ts.URL, strings.NewReader(body))
if err != nil {
    log.Fatal(err)
}
req.Host = "www.example.org"
resp, err := http.DefaultClient.Do(req)
if err != nil {
    log.Fatal(err)
}
defer resp.Body.Close()

b, err := io.ReadAll(resp.Body)
if err != nil {
    log.Fatal(err)
}

fmt.Printf("%s", b)
```

Output:

```go
"POST / HTTP/1.1\r\nHost: www.example.org\r\nAccept-Encoding: gzip\r\nContent-Length: 75\r\nUser-Agent: Go-http-client/1.1\r\n\r\nGo is a general-purpose language designed with systems programming in mind."
```

func DumpRequestOut 
-------------------

```go
func DumpRequestOut(req *http.Request, body bool) ([]byte, error)
```

DumpRequestOut is like DumpRequest but for outgoing client requests. It
includes any headers that the standard http.Transport adds, such as
User-Agent.

#### [Example]

Code:

```go
const body = "Go is a general-purpose language designed with systems programming in mind."
req, err := http.NewRequest("PUT", "http://www.example.org", strings.NewReader(body))
if err != nil {
    log.Fatal(err)
}

dump, err := httputil.DumpRequestOut(req, true)
if err != nil {
    log.Fatal(err)
}

fmt.Printf("%q", dump)
```

Output:

```go
"PUT / HTTP/1.1\r\nHost: www.example.org\r\nUser-Agent: Go-http-client/1.1\r\nContent-Length: 75\r\nAccept-Encoding: gzip\r\n\r\nGo is a general-purpose language designed with systems programming in mind."
```

func DumpResponse 
-----------------

```go
func DumpResponse(resp *http.Response, body bool) ([]byte, error)
```

DumpResponse is like DumpRequest but dumps a response.

#### [Example]

Code:

```go
const body = "Go is a general-purpose language designed with systems programming in mind."
ts := httptest.NewServer(http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
    w.Header().Set("Date", "Wed, 19 Jul 1972 19:00:00 GMT")
    fmt.Fprintln(w, body)
}))
defer ts.Close()

resp, err := http.Get(ts.URL)
if err != nil {
    log.Fatal(err)
}
defer resp.Body.Close()

dump, err := httputil.DumpResponse(resp, true)
if err != nil {
    log.Fatal(err)
}

fmt.Printf("%q", dump)
```

Output:

```go
"HTTP/1.1 200 OK\r\nContent-Length: 76\r\nContent-Type: text/plain; charset=utf-8\r\nDate: Wed, 19 Jul 1972 19:00:00 GMT\r\n\r\nGo is a general-purpose language designed with systems programming in mind.\n"
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
header. Using NewChunkedWriter inside a handler would result in double
chunking or chunking with a Content-Length length, both of which are
wrong.

type BufferPool 
----------------------------------------------

A BufferPool is an interface for getting and returning temporary byte
slices for use by io.CopyBuffer.

```go
type BufferPool interface {
    Get() []byte
    Put([]byte)
}
```

type ClientConn 
---------------

ClientConn is an artifact of Go\'s early HTTP implementation. It is
low-level, old, and unused by Go\'s current HTTP stack. We should have
deleted it before Go 1.

Deprecated: Use Client or Transport in package net/http instead.

```go
type ClientConn struct {
    // contains filtered or unexported fields
}
```

### func NewClientConn 

```go
func NewClientConn(c net.Conn, r *bufio.Reader) *ClientConn
```

NewClientConn is an artifact of Go\'s early HTTP implementation. It is
low-level, old, and unused by Go\'s current HTTP stack. We should have
deleted it before Go 1.

Deprecated: Use the Client or Transport in package net/http instead.

### func NewProxyClientConn 

```go
func NewProxyClientConn(c net.Conn, r *bufio.Reader) *ClientConn
```

NewProxyClientConn is an artifact of Go\'s early HTTP implementation. It
is low-level, old, and unused by Go\'s current HTTP stack. We should
have deleted it before Go 1.

Deprecated: Use the Client or Transport in package net/http instead.

### func (\*ClientConn) Close 

```go
func (cc *ClientConn) Close() error
```

Close calls Hijack and then also closes the underlying connection.

### func (\*ClientConn) Do 

```go
func (cc *ClientConn) Do(req *http.Request) (*http.Response, error)
```

Do is convenience method that writes a request and reads a response.

### func (\*ClientConn) Hijack 

```go
func (cc *ClientConn) Hijack() (c net.Conn, r *bufio.Reader)
```

Hijack detaches the ClientConn and returns the underlying connection as
well as the read-side bufio which may have some left over data. Hijack
may be called before the user or Read have signaled the end of the
keep-alive logic. The user should not call Hijack while Read or Write is
in progress.

### func (\*ClientConn) Pending 

```go
func (cc *ClientConn) Pending() int
```

Pending returns the number of unanswered requests that have been sent on
the connection.

### func (\*ClientConn) Read 

```go
func (cc *ClientConn) Read(req *http.Request) (resp *http.Response, err error)
```

Read reads the next response from the wire. A valid response might be
returned together with an ErrPersistEOF, which means that the remote
requested that this be the last request serviced. Read can be called
concurrently with Write, but not with another Read.

### func (\*ClientConn) Write 

```go
func (cc *ClientConn) Write(req *http.Request) error
```

Write writes a request. An ErrPersistEOF error is returned if the
connection has been closed in an HTTP keep-alive sense. If req.Close
equals true, the keep-alive connection is logically closed after this
request and the opposing server is informed. An ErrUnexpectedEOF
indicates the remote closed the underlying TCP connection, which is
usually considered as graceful close.

type ProxyRequest 
--------------------------------------------------

A ProxyRequest contains a request to be rewritten by a ReverseProxy.

```go
type ProxyRequest struct {
    // In is the request received by the proxy.
    // The Rewrite function must not modify In.
    In *http.Request

    // Out is the request which will be sent by the proxy.
    // The Rewrite function may modify or replace this request.
    // Hop-by-hop headers are removed from this request
    // before Rewrite is called.
    Out *http.Request
}
```

### func (\*ProxyRequest) SetURL 

```go
func (r *ProxyRequest) SetURL(target *url.URL)
```

SetURL routes the outbound request to the scheme, host, and base path
provided in target. If the target\'s path is \"/base\" and the incoming
request was for \"/dir\", the target request will be for \"/base/dir\".

SetURL rewrites the outbound Host header to match the target\'s host. To
preserve the inbound request\'s Host header (the default behavior of
NewSingleHostReverseProxy):

```go
rewriteFunc := func(r *httputil.ProxyRequest) {
    r.SetURL(url)
    r.Out.Host = r.In.Host
}
```

### func (\*ProxyRequest) SetXForwarded 

```go
func (r *ProxyRequest) SetXForwarded()
```

SetXForwarded sets the X-Forwarded-For, X-Forwarded-Host, and
X-Forwarded-Proto headers of the outbound request.

-   The X-Forwarded-For header is set to the client IP address.
-   The X-Forwarded-Host header is set to the host name requested by the
    client.
-   The X-Forwarded-Proto header is set to \"http\" or \"https\",
    depending on whether the inbound request was made on a TLS-enabled
    connection.

If the outbound request contains an existing X-Forwarded-For header,
SetXForwarded appends the client IP address to it. To append to the
inbound request\'s X-Forwarded-For header (the default behavior of
ReverseProxy when using a Director function), copy the header from the
inbound request before calling SetXForwarded:

```go
rewriteFunc := func(r *httputil.ProxyRequest) {
    r.Out.Header["X-Forwarded-For"] = r.In.Header["X-Forwarded-For"]
    r.SetXForwarded()
}
```

type ReverseProxy 
-----------------

ReverseProxy is an HTTP Handler that takes an incoming request and sends
it to another server, proxying the response back to the client.

1xx responses are forwarded to the client if the underlying transport
supports ClientTrace.Got1xxResponse.

```go
type ReverseProxy struct {
    // Rewrite must be a function which modifies
    // the request into a new request to be sent
    // using Transport. Its response is then copied
    // back to the original client unmodified.
    // Rewrite must not access the provided ProxyRequest
    // or its contents after returning.
    //
    // The Forwarded, X-Forwarded, X-Forwarded-Host,
    // and X-Forwarded-Proto headers are removed from the
    // outbound request before Rewrite is called. See also
    // the ProxyRequest.SetXForwarded method.
    //
    // Unparsable query parameters are removed from the
    // outbound request before Rewrite is called.
    // The Rewrite function may copy the inbound URL's
    // RawQuery to the outbound URL to preserve the original
    // parameter string. Note that this can lead to security
    // issues if the proxy's interpretation of query parameters
    // does not match that of the downstream server.
    //
    // At most one of Rewrite or Director may be set.
    Rewrite func(*ProxyRequest) // Go 1.20

    // Director is a function which modifies
    // the request into a new request to be sent
    // using Transport. Its response is then copied
    // back to the original client unmodified.
    // Director must not access the provided Request
    // after returning.
    //
    // By default, the X-Forwarded-For header is set to the
    // value of the client IP address. If an X-Forwarded-For
    // header already exists, the client IP is appended to the
    // existing values. As a special case, if the header
    // exists in the Request.Header map but has a nil value
    // (such as when set by the Director func), the X-Forwarded-For
    // header is not modified.
    //
    // To prevent IP spoofing, be sure to delete any pre-existing
    // X-Forwarded-For header coming from the client or
    // an untrusted proxy.
    //
    // Hop-by-hop headers are removed from the request after
    // Director returns, which can remove headers added by
    // Director. Use a Rewrite function instead to ensure
    // modifications to the request are preserved.
    //
    // Unparsable query parameters are removed from the outbound
    // request if Request.Form is set after Director returns.
    //
    // At most one of Rewrite or Director may be set.
    Director func(*http.Request)

    // The transport used to perform proxy requests.
    // If nil, http.DefaultTransport is used.
    Transport http.RoundTripper

    // FlushInterval specifies the flush interval
    // to flush to the client while copying the
    // response body.
    // If zero, no periodic flushing is done.
    // A negative value means to flush immediately
    // after each write to the client.
    // The FlushInterval is ignored when ReverseProxy
    // recognizes a response as a streaming response, or
    // if its ContentLength is -1; for such responses, writes
    // are flushed to the client immediately.
    FlushInterval time.Duration

    // ErrorLog specifies an optional logger for errors
    // that occur when attempting to proxy the request.
    // If nil, logging is done via the log package's standard logger.
    ErrorLog *log.Logger // Go 1.4

    // BufferPool optionally specifies a buffer pool to
    // get byte slices for use by io.CopyBuffer when
    // copying HTTP response bodies.
    BufferPool BufferPool // Go 1.6

    // ModifyResponse is an optional function that modifies the
    // Response from the backend. It is called if the backend
    // returns a response at all, with any HTTP status code.
    // If the backend is unreachable, the optional ErrorHandler is
    // called without any call to ModifyResponse.
    //
    // If ModifyResponse returns an error, ErrorHandler is called
    // with its error value. If ErrorHandler is nil, its default
    // implementation is used.
    ModifyResponse func(*http.Response) error // Go 1.8

    // ErrorHandler is an optional function that handles errors
    // reaching the backend or errors from ModifyResponse.
    //
    // If nil, the default is to log the provided error and return
    // a 502 Status Bad Gateway response.
    ErrorHandler func(http.ResponseWriter, *http.Request, error) // Go 1.11
}
```

#### [Example]

Code:

```go
backendServer := httptest.NewServer(http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintln(w, "this call was relayed by the reverse proxy")
}))
defer backendServer.Close()

rpURL, err := url.Parse(backendServer.URL)
if err != nil {
    log.Fatal(err)
}
frontendProxy := httptest.NewServer(&httputil.ReverseProxy{
    Rewrite: func(r *httputil.ProxyRequest) {
        r.SetXForwarded()
        r.SetURL(rpURL)
    },
})
defer frontendProxy.Close()

resp, err := http.Get(frontendProxy.URL)
if err != nil {
    log.Fatal(err)
}

b, err := io.ReadAll(resp.Body)
if err != nil {
    log.Fatal(err)
}

fmt.Printf("%s", b)
```

Output:

```go
this call was relayed by the reverse proxy
```

### func NewSingleHostReverseProxy 

```go
func NewSingleHostReverseProxy(target *url.URL) *ReverseProxy
```

NewSingleHostReverseProxy returns a new ReverseProxy that routes URLs to
the scheme, host, and base path provided in target. If the target\'s
path is \"/base\" and the incoming request was for \"/dir\", the target
request will be for /base/dir.

NewSingleHostReverseProxy does not rewrite the Host header.

To customize the ReverseProxy behavior beyond what
NewSingleHostReverseProxy provides, use ReverseProxy directly with a
Rewrite function. The ProxyRequest SetURL method may be used to route
the outbound request. (Note that SetURL, unlike
NewSingleHostReverseProxy, rewrites the Host header of the outbound
request by default.)

```go
proxy := &ReverseProxy{
    Rewrite: func(r *ProxyRequest) {
        r.SetURL(target)
        r.Out.Host = r.In.Host // if desired
    },
}
```

### func (\*ReverseProxy) ServeHTTP 

```go
func (p *ReverseProxy) ServeHTTP(rw http.ResponseWriter, req *http.Request)
```

type ServerConn 
---------------

ServerConn is an artifact of Go\'s early HTTP implementation. It is
low-level, old, and unused by Go\'s current HTTP stack. We should have
deleted it before Go 1.

Deprecated: Use the Server in package net/http instead.

```go
type ServerConn struct {
    // contains filtered or unexported fields
}
```

### func NewServerConn 

```go
func NewServerConn(c net.Conn, r *bufio.Reader) *ServerConn
```

NewServerConn is an artifact of Go\'s early HTTP implementation. It is
low-level, old, and unused by Go\'s current HTTP stack. We should have
deleted it before Go 1.

Deprecated: Use the Server in package net/http instead.

### func (\*ServerConn) Close 

```go
func (sc *ServerConn) Close() error
```

Close calls Hijack and then also closes the underlying connection.

### func (\*ServerConn) Hijack 

```go
func (sc *ServerConn) Hijack() (net.Conn, *bufio.Reader)
```

Hijack detaches the ServerConn and returns the underlying connection as
well as the read-side bufio which may have some left over data. Hijack
may be called before Read has signaled the end of the keep-alive logic.
The user should not call Hijack while Read or Write is in progress.

### func (\*ServerConn) Pending 

```go
func (sc *ServerConn) Pending() int
```

Pending returns the number of unanswered requests that have been
received on the connection.

### func (\*ServerConn) Read 

```go
func (sc *ServerConn) Read() (*http.Request, error)
```

Read returns the next request on the wire. An ErrPersistEOF is returned
if it is gracefully determined that there are no more requests (e.g.
after the first request on an HTTP/1.0 connection, or after a
Connection:close on a HTTP/1.1 connection).

### func (\*ServerConn) Write 

```go
func (sc *ServerConn) Write(req *http.Request, resp *http.Response) error
```

Write writes resp in response to req. To close the connection
gracefully, set the Response.Close field to true. Write should be
considered operational until it returns an error, regardless of any
errors returned on the Read side.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/net/http/httputil/>

