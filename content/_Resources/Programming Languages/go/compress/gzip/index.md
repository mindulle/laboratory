Package gzip
============

-   `import "compress/gzip"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package gzip implements reading and writing of gzip format compressed
files, as specified in RFC 1952.

#### [Example (CompressingReader)]

Code:

```go
// This is an example of writing a compressing reader.
// This can be useful for an HTTP client body, as shown.

const testdata = "the data to be compressed"

// This HTTP handler is just for testing purposes.
handler := http.HandlerFunc(func(rw http.ResponseWriter, req *http.Request) {
    zr, err := gzip.NewReader(req.Body)
    if err != nil {
        log.Fatal(err)
    }

    // Just output the data for the example.
    if _, err := io.Copy(os.Stdout, zr); err != nil {
        log.Fatal(err)
    }
})
ts := httptest.NewServer(handler)
defer ts.Close()

// The remainder is the example code.

// The data we want to compress, as an io.Reader
dataReader := strings.NewReader(testdata)

// bodyReader is the body of the HTTP request, as an io.Reader.
// httpWriter is the body of the HTTP request, as an io.Writer.
bodyReader, httpWriter := io.Pipe()

// Make sure that bodyReader is always closed, so that the
// goroutine below will always exit.
defer bodyReader.Close()

// gzipWriter compresses data to httpWriter.
gzipWriter := gzip.NewWriter(httpWriter)

// errch collects any errors from the writing goroutine.
errch := make(chan error, 1)

go func() {
    defer close(errch)
    sentErr := false
    sendErr := func(err error) {
        if !sentErr {
            errch <- err
            sentErr = true
        }
    }

    // Copy our data to gzipWriter, which compresses it to
    // gzipWriter, which feeds it to bodyReader.
    if _, err := io.Copy(gzipWriter, dataReader); err != nil && err != io.ErrClosedPipe {
        sendErr(err)
    }
    if err := gzipWriter.Close(); err != nil && err != io.ErrClosedPipe {
        sendErr(err)
    }
    if err := httpWriter.Close(); err != nil && err != io.ErrClosedPipe {
        sendErr(err)
    }
}()

// Send an HTTP request to the test server.
req, err := http.NewRequest("PUT", ts.URL, bodyReader)
if err != nil {
    log.Fatal(err)
}

// Note that passing req to http.Client.Do promises that it
// will close the body, in this case bodyReader.
resp, err := ts.Client().Do(req)
if err != nil {
    log.Fatal(err)
}

// Check whether there was an error compressing the data.
if err := <-errch; err != nil {
    log.Fatal(err)
}

// For this example we don't care about the response.
resp.Body.Close()
```

Output:

```go
the data to be compressed
```

#### [Example (WriterReader)]

Code:

```go
var buf bytes.Buffer
zw := gzip.NewWriter(&buf)

// Setting the Header fields is optional.
zw.Name = "a-new-hope.txt"
zw.Comment = "an epic space opera by George Lucas"
zw.ModTime = time.Date(1977, time.May, 25, 0, 0, 0, 0, time.UTC)

_, err := zw.Write([]byte("A long time ago in a galaxy far, far away..."))
if err != nil {
    log.Fatal(err)
}

if err := zw.Close(); err != nil {
    log.Fatal(err)
}

zr, err := gzip.NewReader(&buf)
if err != nil {
    log.Fatal(err)
}

fmt.Printf("Name: %s\nComment: %s\nModTime: %s\n\n", zr.Name, zr.Comment, zr.ModTime.UTC())

if _, err := io.Copy(os.Stdout, zr); err != nil {
    log.Fatal(err)
}

if err := zr.Close(); err != nil {
    log.Fatal(err)
}
```

Output:

```go
Name: a-new-hope.txt
Comment: an epic space opera by George Lucas
ModTime: 1977-05-25 00:00:00 +0000 UTC

A long time ago in a galaxy far, far away...
```

Index 
-----

-   [Constants](#pkg-constants)
-   [Variables](#pkg-variables)
-   [type Header](#Header)
-   [type Reader](#Reader)
-   [func NewReader(r io.Reader) (\*Reader, error)](#NewReader)
-   [func (z \*Reader) Close() error](#Reader.Close)
-   [func (z \*Reader) Multistream(ok bool)](#Reader.Multistream)
-   [func (z \*Reader) Read(p \[\]byte) (n int, err
    error)](#Reader.Read)
-   [func (z \*Reader) Reset(r io.Reader) error](#Reader.Reset)
-   [type Writer](#Writer)
-   [func NewWriter(w io.Writer) \*Writer](#NewWriter)
-   [func NewWriterLevel(w io.Writer, level int) (\*Writer,
    error)](#NewWriterLevel)
-   [func (z \*Writer) Close() error](#Writer.Close)
-   [func (z \*Writer) Flush() error](#Writer.Flush)
-   [func (z \*Writer) Reset(w io.Writer)](#Writer.Reset)
-   [func (z \*Writer) Write(p \[\]byte) (int, error)](#Writer.Write)

 
### Examples

[Reader.Multistream](#example_Reader_Multistream)

[Package (CompressingReader)](#example__compressingReader)

[Package (WriterReader)](#example__writerReader)


### Package files

gunzip.go gzip.go

Constants 
---------

These constants are copied from the flate package, so that code that
imports \"compress/gzip\" does not also have to import
\"compress/flate\".

```go
const (
    NoCompression      = flate.NoCompression
    BestSpeed          = flate.BestSpeed
    BestCompression    = flate.BestCompression
    DefaultCompression = flate.DefaultCompression
    HuffmanOnly        = flate.HuffmanOnly
)
```

Variables 
---------

```go
var (
    // ErrChecksum is returned when reading GZIP data that has an invalid checksum.
    ErrChecksum = errors.New("gzip: invalid checksum")
    // ErrHeader is returned when reading GZIP data that has an invalid header.
    ErrHeader = errors.New("gzip: invalid header")
)
```

type Header 
-----------

The gzip file stores a header giving metadata about the compressed file.
That header is exposed as the fields of the Writer and Reader structs.

Strings must be UTF-8 encoded and may only contain Unicode code points
U+0001 through U+00FF, due to limitations of the GZIP file format.

```go
type Header struct {
    Comment string    // comment
    Extra   []byte    // "extra data"
    ModTime time.Time // modification time
    Name    string    // file name
    OS      byte      // operating system type
}
```

type Reader 
-----------

A Reader is an io.Reader that can be read to retrieve uncompressed data
from a gzip-format compressed file.

In general, a gzip file can be a concatenation of gzip files, each with
its own header. Reads from the Reader return the concatenation of the
uncompressed data of each. Only the first header is recorded in the
Reader fields.

Gzip files store a length and checksum of the uncompressed data. The
Reader will return an ErrChecksum when Read reaches the end of the
uncompressed data if it does not have the expected length or checksum.
Clients should treat data returned by Read as tentative until they
receive the io.EOF marking the end of the data.

```go
type Reader struct {
    Header // valid after NewReader or Reader.Reset
    // contains filtered or unexported fields
}
```

### func NewReader 

```go
func NewReader(r io.Reader) (*Reader, error)
```

NewReader creates a new Reader reading the given reader. If r does not
also implement io.ByteReader, the decompressor may read more data than
necessary from r.

It is the caller\'s responsibility to call Close on the Reader when
done.

The Reader.Header fields will be valid in the Reader returned.

### func (\*Reader) Close 

```go
func (z *Reader) Close() error
```

Close closes the Reader. It does not close the underlying io.Reader. In
order for the GZIP checksum to be verified, the reader must be fully
consumed until the io.EOF.

### func (\*Reader) Multistream 

```go
func (z *Reader) Multistream(ok bool)
```

Multistream controls whether the reader supports multistream files.

If enabled (the default), the Reader expects the input to be a sequence
of individually gzipped data streams, each with its own header and
trailer, ending at EOF. The effect is that the concatenation of a
sequence of gzipped files is treated as equivalent to the gzip of the
concatenation of the sequence. This is standard behavior for gzip
readers.

Calling Multistream(false) disables this behavior; disabling the
behavior can be useful when reading file formats that distinguish
individual gzip data streams or mix gzip data streams with other data
streams. In this mode, when the Reader reaches the end of the data
stream, Read returns io.EOF. The underlying reader must implement
io.ByteReader in order to be left positioned just after the gzip stream.
To start the next stream, call z.Reset(r) followed by
z.Multistream(false). If there is no next stream, z.Reset(r) will return
io.EOF.

#### [Example]

Code:

```go
var buf bytes.Buffer
zw := gzip.NewWriter(&buf)

var files = []struct {
    name    string
    comment string
    modTime time.Time
    data    string
}{
    {"file-1.txt", "file-header-1", time.Date(2006, time.February, 1, 3, 4, 5, 0, time.UTC), "Hello Gophers - 1"},
    {"file-2.txt", "file-header-2", time.Date(2007, time.March, 2, 4, 5, 6, 1, time.UTC), "Hello Gophers - 2"},
}

for _, file := range files {
    zw.Name = file.name
    zw.Comment = file.comment
    zw.ModTime = file.modTime

    if _, err := zw.Write([]byte(file.data)); err != nil {
        log.Fatal(err)
    }

    if err := zw.Close(); err != nil {
        log.Fatal(err)
    }

    zw.Reset(&buf)
}

zr, err := gzip.NewReader(&buf)
if err != nil {
    log.Fatal(err)
}

for {
    zr.Multistream(false)
    fmt.Printf("Name: %s\nComment: %s\nModTime: %s\n\n", zr.Name, zr.Comment, zr.ModTime.UTC())

    if _, err := io.Copy(os.Stdout, zr); err != nil {
        log.Fatal(err)
    }

    fmt.Print("\n\n")

    err = zr.Reset(&buf)
    if err == io.EOF {
        break
    }
    if err != nil {
        log.Fatal(err)
    }
}

if err := zr.Close(); err != nil {
    log.Fatal(err)
}
```

Output:

```go
Name: file-1.txt
Comment: file-header-1
ModTime: 2006-02-01 03:04:05 +0000 UTC

Hello Gophers - 1

Name: file-2.txt
Comment: file-header-2
ModTime: 2007-03-02 04:05:06 +0000 UTC

Hello Gophers - 2
```

### func (\*Reader) Read 

```go
func (z *Reader) Read(p []byte) (n int, err error)
```

Read implements io.Reader, reading uncompressed bytes from its
underlying Reader.

### func (\*Reader) Reset 

```go
func (z *Reader) Reset(r io.Reader) error
```

Reset discards the Reader z\'s state and makes it equivalent to the
result of its original state from NewReader, but reading from r instead.
This permits reusing a Reader rather than allocating a new one.

type Writer 
-----------

A Writer is an io.WriteCloser. Writes to a Writer are compressed and
written to w.

```go
type Writer struct {
    Header // written at first call to Write, Flush, or Close
    // contains filtered or unexported fields
}
```

### func NewWriter 

```go
func NewWriter(w io.Writer) *Writer
```

NewWriter returns a new Writer. Writes to the returned writer are
compressed and written to w.

It is the caller\'s responsibility to call Close on the Writer when
done. Writes may be buffered and not flushed until Close.

Callers that wish to set the fields in Writer.Header must do so before
the first call to Write, Flush, or Close.

### func NewWriterLevel 

```go
func NewWriterLevel(w io.Writer, level int) (*Writer, error)
```

NewWriterLevel is like NewWriter but specifies the compression level
instead of assuming DefaultCompression.

The compression level can be DefaultCompression, NoCompression,
HuffmanOnly or any integer value between BestSpeed and BestCompression
inclusive. The error returned will be nil if the level is valid.

### func (\*Writer) Close 

```go
func (z *Writer) Close() error
```

Close closes the Writer by flushing any unwritten data to the underlying
io.Writer and writing the GZIP footer. It does not close the underlying
io.Writer.

### func (\*Writer) Flush 

```go
func (z *Writer) Flush() error
```

Flush flushes any pending compressed data to the underlying writer.

It is useful mainly in compressed network protocols, to ensure that a
remote reader has enough data to reconstruct a packet. Flush does not
return until the data has been written. If the underlying writer returns
an error, Flush returns that error.

In the terminology of the zlib library, Flush is equivalent to
Z\_SYNC\_FLUSH.

### func (\*Writer) Reset 

```go
func (z *Writer) Reset(w io.Writer)
```

Reset discards the Writer z\'s state and makes it equivalent to the
result of its original state from NewWriter or NewWriterLevel, but
writing to w instead. This permits reusing a Writer rather than
allocating a new one.

### func (\*Writer) Write 

```go
func (z *Writer) Write(p []byte) (int, error)
```

Write writes a compressed form of p to the underlying io.Writer. The
compressed bytes are not necessarily flushed until the Writer is closed.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/compress/gzip/>

