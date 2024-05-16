Package quotedprintable
=======================

-   `import "mime/quotedprintable"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package quotedprintable implements quoted-printable encoding as
specified by RFC 2045.

Index 
-----

-   [type Reader](#Reader)
-   [func NewReader(r io.Reader) \*Reader](#NewReader)
-   [func (r \*Reader) Read(p \[\]byte) (n int, err
    error)](#Reader.Read)
-   [type Writer](#Writer)
-   [func NewWriter(w io.Writer) \*Writer](#NewWriter)
-   [func (w \*Writer) Close() error](#Writer.Close)
-   [func (w \*Writer) Write(p \[\]byte) (n int, err
    error)](#Writer.Write)

 
### Examples

[NewReader](#example_NewReader)

[NewWriter](#example_NewWriter)


### Package files

reader.go writer.go

type Reader 
------------------------------------------

Reader is a quoted-printable decoder.

```go
type Reader struct {
    // contains filtered or unexported fields
}
```

### func NewReader 

```go
func NewReader(r io.Reader) *Reader
```

NewReader returns a quoted-printable reader, decoding from r.

#### [Example]

Code:

```go
for _, s := range []string{
    `=48=65=6C=6C=6F=2C=20=47=6F=70=68=65=72=73=21`,
    `invalid escape: <b style="font-size: 200%">hello</b>`,
    "Hello, Gophers! This symbol will be unescaped: =3D and this will be written in =\r\none line.",
} {
    b, err := io.ReadAll(quotedprintable.NewReader(strings.NewReader(s)))
    fmt.Printf("%s %v\n", b, err)
}
```

Output:

```go
Hello, Gophers! <nil>
invalid escape: <b style="font-size: 200%">hello</b> <nil>
Hello, Gophers! This symbol will be unescaped: = and this will be written in one line. <nil>
```

### func (\*Reader) Read 

```go
func (r *Reader) Read(p []byte) (n int, err error)
```

Read reads and decodes quoted-printable data from the underlying reader.

type Writer 
------------------------------------------

A Writer is a quoted-printable writer that implements io.WriteCloser.

```go
type Writer struct {
    // Binary mode treats the writer's input as pure binary and processes end of
    // line bytes as binary data.
    Binary bool
    // contains filtered or unexported fields
}
```

### func NewWriter 

```go
func NewWriter(w io.Writer) *Writer
```

NewWriter returns a new Writer that writes to w.

#### [Example]

Code:

```go
w := quotedprintable.NewWriter(os.Stdout)
w.Write([]byte("These symbols will be escaped: = \t"))
w.Close()
```

Output:

```go
These symbols will be escaped: =3D =09
```

### func (\*Writer) Close 

```go
func (w *Writer) Close() error
```

Close closes the Writer, flushing any unwritten data to the underlying
io.Writer, but does not close the underlying io.Writer.

### func (\*Writer) Write 

```go
func (w *Writer) Write(p []byte) (n int, err error)
```

Write encodes p using quoted-printable encoding and writes it to the
underlying io.Writer. It limits line length to 76 characters. The
encoded bytes are not necessarily flushed until the Writer is closed.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/mime/quotedprintable/>

