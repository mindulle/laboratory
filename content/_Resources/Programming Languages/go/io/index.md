Package io
==========

-   `import "io"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)
-   [Subdirectories](#pkg-subdirectories)

Overview 
--------

Package io provides basic interfaces to I/O primitives. Its primary job
is to wrap existing implementations of such primitives, such as those in
package os, into shared public interfaces that abstract the
functionality, plus some other related primitives.

Because these interfaces and primitives wrap lower-level operations with
various implementations, unless otherwise informed clients should not
assume they are safe for parallel execution.

Index 
-----

-   [Constants](#pkg-constants)
-   [Variables](#pkg-variables)
-   [func Copy(dst Writer, src Reader) (written int64, err
    error)](#Copy)
-   [func CopyBuffer(dst Writer, src Reader, buf \[\]byte) (written
    int64, err error)](#CopyBuffer)
-   [func CopyN(dst Writer, src Reader, n int64) (written int64, err
    error)](#CopyN)
-   [func Pipe() (\*PipeReader, \*PipeWriter)](#Pipe)
-   [func ReadAll(r Reader) (\[\]byte, error)](#ReadAll)
-   [func ReadAtLeast(r Reader, buf \[\]byte, min int) (n int, err
    error)](#ReadAtLeast)
-   [func ReadFull(r Reader, buf \[\]byte) (n int, err
    error)](#ReadFull)
-   [func WriteString(w Writer, s string) (n int, err
    error)](#WriteString)
-   [type ByteReader](#ByteReader)
-   [type ByteScanner](#ByteScanner)
-   [type ByteWriter](#ByteWriter)
-   [type Closer](#Closer)
-   [type LimitedReader](#LimitedReader)
-   [func (l \*LimitedReader) Read(p \[\]byte) (n int, err
    error)](#LimitedReader.Read)
-   [type OffsetWriter](#OffsetWriter)
-   [func NewOffsetWriter(w WriterAt, off int64)
    \*OffsetWriter](#NewOffsetWriter)
-   [func (o \*OffsetWriter) Seek(offset int64, whence int) (int64,
    error)](#OffsetWriter.Seek)
-   [func (o \*OffsetWriter) Write(p \[\]byte) (n int, err
    error)](#OffsetWriter.Write)
-   [func (o \*OffsetWriter) WriteAt(p \[\]byte, off int64) (n int, err
    error)](#OffsetWriter.WriteAt)
-   [type PipeReader](#PipeReader)
-   [func (r \*PipeReader) Close() error](#PipeReader.Close)
-   [func (r \*PipeReader) CloseWithError(err error)
    error](#PipeReader.CloseWithError)
-   [func (r \*PipeReader) Read(data \[\]byte) (n int, err
    error)](#PipeReader.Read)
-   [type PipeWriter](#PipeWriter)
-   [func (w \*PipeWriter) Close() error](#PipeWriter.Close)
-   [func (w \*PipeWriter) CloseWithError(err error)
    error](#PipeWriter.CloseWithError)
-   [func (w \*PipeWriter) Write(data \[\]byte) (n int, err
    error)](#PipeWriter.Write)
-   [type ReadCloser](#ReadCloser)
-   [func NopCloser(r Reader) ReadCloser](#NopCloser)
-   [type ReadSeekCloser](#ReadSeekCloser)
-   [type ReadSeeker](#ReadSeeker)
-   [type ReadWriteCloser](#ReadWriteCloser)
-   [type ReadWriteSeeker](#ReadWriteSeeker)
-   [type ReadWriter](#ReadWriter)
-   [type Reader](#Reader)
-   [func LimitReader(r Reader, n int64) Reader](#LimitReader)
-   [func MultiReader(readers \...Reader) Reader](#MultiReader)
-   [func TeeReader(r Reader, w Writer) Reader](#TeeReader)
-   [type ReaderAt](#ReaderAt)
-   [type ReaderFrom](#ReaderFrom)
-   [type RuneReader](#RuneReader)
-   [type RuneScanner](#RuneScanner)
-   [type SectionReader](#SectionReader)
-   [func NewSectionReader(r ReaderAt, off int64, n int64)
    \*SectionReader](#NewSectionReader)
-   [func (s \*SectionReader) Read(p \[\]byte) (n int, err
    error)](#SectionReader.Read)
-   [func (s \*SectionReader) ReadAt(p \[\]byte, off int64) (n int, err
    error)](#SectionReader.ReadAt)
-   [func (s \*SectionReader) Seek(offset int64, whence int) (int64,
    error)](#SectionReader.Seek)
-   [func (s \*SectionReader) Size() int64](#SectionReader.Size)
-   [type Seeker](#Seeker)
-   [type StringWriter](#StringWriter)
-   [type WriteCloser](#WriteCloser)
-   [type WriteSeeker](#WriteSeeker)
-   [type Writer](#Writer)
-   [func MultiWriter(writers \...Writer) Writer](#MultiWriter)
-   [type WriterAt](#WriterAt)
-   [type WriterTo](#WriterTo)

 
### Examples

[Copy](#example_Copy)

[CopyBuffer](#example_CopyBuffer)

[CopyN](#example_CopyN)

[LimitReader](#example_LimitReader)

[MultiReader](#example_MultiReader)

[MultiWriter](#example_MultiWriter)

[Pipe](#example_Pipe)

[ReadAll](#example_ReadAll)

[ReadAtLeast](#example_ReadAtLeast)

[ReadFull](#example_ReadFull)

[SectionReader](#example_SectionReader)

[SectionReader.Read](#example_SectionReader_Read)

[SectionReader.ReadAt](#example_SectionReader_ReadAt)

[SectionReader.Seek](#example_SectionReader_Seek)

[SectionReader.Size](#example_SectionReader_Size)

[TeeReader](#example_TeeReader)

[WriteString](#example_WriteString)


### Package files

io.go multi.go pipe.go

Constants 
---------

Seek whence values.

```go
const (
    SeekStart   = 0 // seek relative to the origin of the file
    SeekCurrent = 1 // seek relative to the current offset
    SeekEnd     = 2 // seek relative to the end
)
```

Variables 
---------

EOF is the error returned by Read when no more input is available. (Read
must return EOF itself, not an error wrapping EOF, because callers will
test for EOF using ==.) Functions should return EOF only to signal a
graceful end of input. If the EOF occurs unexpectedly in a structured
data stream, the appropriate error is either ErrUnexpectedEOF or some
other error giving more detail.

```go
var EOF = errors.New("EOF")
```

ErrClosedPipe is the error used for read or write operations on a closed
pipe.

```go
var ErrClosedPipe = errors.New("io: read/write on closed pipe")
```

ErrNoProgress is returned by some clients of a Reader when many calls to
Read have failed to return any data or error, usually the sign of a
broken Reader implementation.

```go
var ErrNoProgress = errors.New("multiple Read calls return no data or error")
```

ErrShortBuffer means that a read required a longer buffer than was
provided.

```go
var ErrShortBuffer = errors.New("short buffer")
```

ErrShortWrite means that a write accepted fewer bytes than requested but
failed to return an explicit error.

```go
var ErrShortWrite = errors.New("short write")
```

ErrUnexpectedEOF means that EOF was encountered in the middle of reading
a fixed-size block or data structure.

```go
var ErrUnexpectedEOF = errors.New("unexpected EOF")
```

func Copy 
---------

```go
func Copy(dst Writer, src Reader) (written int64, err error)
```

Copy copies from src to dst until either EOF is reached on src or an
error occurs. It returns the number of bytes copied and the first error
encountered while copying, if any.

A successful Copy returns err == nil, not err == EOF. Because Copy is
defined to read from src until EOF, it does not treat an EOF from Read
as an error to be reported.

If src implements the WriterTo interface, the copy is implemented by
calling src.WriteTo(dst). Otherwise, if dst implements the ReaderFrom
interface, the copy is implemented by calling dst.ReadFrom(src).

#### [Example]

Code:

```go
r := strings.NewReader("some io.Reader stream to be read\n")

if _, err := io.Copy(os.Stdout, r); err != nil {
    log.Fatal(err)
}
```

Output:

```go
some io.Reader stream to be read
```

func CopyBuffer 
----------------------------------------------

```go
func CopyBuffer(dst Writer, src Reader, buf []byte) (written int64, err error)
```

CopyBuffer is identical to Copy except that it stages through the
provided buffer (if one is required) rather than allocating a temporary
one. If buf is nil, one is allocated; otherwise if it has zero length,
CopyBuffer panics.

If either src implements WriterTo or dst implements ReaderFrom, buf will
not be used to perform the copy.

#### [Example]

Code:

```go
r1 := strings.NewReader("first reader\n")
r2 := strings.NewReader("second reader\n")
buf := make([]byte, 8)

// buf is used here...
if _, err := io.CopyBuffer(os.Stdout, r1, buf); err != nil {
    log.Fatal(err)
}

// ... reused here also. No need to allocate an extra buffer.
if _, err := io.CopyBuffer(os.Stdout, r2, buf); err != nil {
    log.Fatal(err)
}
```

Output:

```go
first reader
second reader
```

func CopyN 
----------

```go
func CopyN(dst Writer, src Reader, n int64) (written int64, err error)
```

CopyN copies n bytes (or until an error) from src to dst. It returns the
number of bytes copied and the earliest error encountered while copying.
On return, written == n if and only if err == nil.

If dst implements the ReaderFrom interface, the copy is implemented
using it.

#### [Example]

Code:

```go
r := strings.NewReader("some io.Reader stream to be read")

if _, err := io.CopyN(os.Stdout, r, 4); err != nil {
    log.Fatal(err)
}
```

Output:

```go
some
```

func Pipe 
---------

```go
func Pipe() (*PipeReader, *PipeWriter)
```

Pipe creates a synchronous in-memory pipe. It can be used to connect
code expecting an io.Reader with code expecting an io.Writer.

Reads and Writes on the pipe are matched one to one except when multiple
Reads are needed to consume a single Write. That is, each Write to the
PipeWriter blocks until it has satisfied one or more Reads from the
PipeReader that fully consume the written data. The data is copied
directly from the Write to the corresponding Read (or Reads); there is
no internal buffering.

It is safe to call Read and Write in parallel with each other or with
Close. Parallel calls to Read and parallel calls to Write are also safe:
the individual calls will be gated sequentially.

#### [Example]

Code:

```go
r, w := io.Pipe()

go func() {
    fmt.Fprint(w, "some io.Reader stream to be read\n")
    w.Close()
}()

if _, err := io.Copy(os.Stdout, r); err != nil {
    log.Fatal(err)
}
```

Output:

```go
some io.Reader stream to be read
```

func ReadAll 
---------------------------------------------

```go
func ReadAll(r Reader) ([]byte, error)
```

ReadAll reads from r until an error or EOF and returns the data it read.
A successful call returns err == nil, not err == EOF. Because ReadAll is
defined to read from src until EOF, it does not treat an EOF from Read
as an error to be reported.

#### [Example]

Code:

```go
r := strings.NewReader("Go is a general-purpose language designed with systems programming in mind.")

b, err := io.ReadAll(r)
if err != nil {
    log.Fatal(err)
}

fmt.Printf("%s", b)
```

Output:

```go
Go is a general-purpose language designed with systems programming in mind.
```

func ReadAtLeast 
----------------

```go
func ReadAtLeast(r Reader, buf []byte, min int) (n int, err error)
```

ReadAtLeast reads from r into buf until it has read at least min bytes.
It returns the number of bytes copied and an error if fewer bytes were
read. The error is EOF only if no bytes were read. If an EOF happens
after reading fewer than min bytes, ReadAtLeast returns
ErrUnexpectedEOF. If min is greater than the length of buf, ReadAtLeast
returns ErrShortBuffer. On return, n \>= min if and only if err == nil.
If r returns an error having read at least min bytes, the error is
dropped.

#### [Example]

Code:

```go
r := strings.NewReader("some io.Reader stream to be read\n")

buf := make([]byte, 14)
if _, err := io.ReadAtLeast(r, buf, 4); err != nil {
    log.Fatal(err)
}
fmt.Printf("%s\n", buf)

// buffer smaller than minimal read size.
shortBuf := make([]byte, 3)
if _, err := io.ReadAtLeast(r, shortBuf, 4); err != nil {
    fmt.Println("error:", err)
}

// minimal read size bigger than io.Reader stream
longBuf := make([]byte, 64)
if _, err := io.ReadAtLeast(r, longBuf, 64); err != nil {
    fmt.Println("error:", err)
}
```

Output:

```go
some io.Reader
error: short buffer
error: unexpected EOF
```

func ReadFull 
-------------

```go
func ReadFull(r Reader, buf []byte) (n int, err error)
```

ReadFull reads exactly len(buf) bytes from r into buf. It returns the
number of bytes copied and an error if fewer bytes were read. The error
is EOF only if no bytes were read. If an EOF happens after reading some
but not all the bytes, ReadFull returns ErrUnexpectedEOF. On return, n
== len(buf) if and only if err == nil. If r returns an error having read
at least len(buf) bytes, the error is dropped.

#### [Example]

Code:

```go
r := strings.NewReader("some io.Reader stream to be read\n")

buf := make([]byte, 4)
if _, err := io.ReadFull(r, buf); err != nil {
    log.Fatal(err)
}
fmt.Printf("%s\n", buf)

// minimal read size bigger than io.Reader stream
longBuf := make([]byte, 64)
if _, err := io.ReadFull(r, longBuf); err != nil {
    fmt.Println("error:", err)
}
```

Output:

```go
some
error: unexpected EOF
```

func WriteString 
----------------

```go
func WriteString(w Writer, s string) (n int, err error)
```

WriteString writes the contents of the string s to w, which accepts a
slice of bytes. If w implements StringWriter, its WriteString method is
invoked directly. Otherwise, w.Write is called exactly once.

#### [Example]

Code:

```go
if _, err := io.WriteString(os.Stdout, "Hello World"); err != nil {
    log.Fatal(err)
}
```

Output:

```go
Hello World
```

type ByteReader 
---------------

ByteReader is the interface that wraps the ReadByte method.

ReadByte reads and returns the next byte from the input or any error
encountered. If ReadByte returns an error, no input byte was consumed,
and the returned byte value is undefined.

ReadByte provides an efficient interface for byte-at-time processing. A
Reader that does not implement ByteReader can be wrapped using
bufio.NewReader to add this method.

```go
type ByteReader interface {
    ReadByte() (byte, error)
}
```

type ByteScanner 
----------------

ByteScanner is the interface that adds the UnreadByte method to the
basic ReadByte method.

UnreadByte causes the next call to ReadByte to return the last byte
read. If the last operation was not a successful call to ReadByte,
UnreadByte may return an error, unread the last byte read (or the byte
prior to the last-unread byte), or (in implementations that support the
Seeker interface) seek to one byte before the current offset.

```go
type ByteScanner interface {
    ByteReader
    UnreadByte() error
}
```

type ByteWriter 
----------------------------------------------

ByteWriter is the interface that wraps the WriteByte method.

```go
type ByteWriter interface {
    WriteByte(c byte) error
}
```

type Closer 
-----------

Closer is the interface that wraps the basic Close method.

The behavior of Close after the first call is undefined. Specific
implementations may document their own behavior.

```go
type Closer interface {
    Close() error
}
```

type LimitedReader 
------------------

A LimitedReader reads from R but limits the amount of data returned to
just N bytes. Each call to Read updates N to reflect the new amount
remaining. Read returns EOF when N \<= 0 or when the underlying R
returns EOF.

```go
type LimitedReader struct {
    R Reader // underlying reader
    N int64  // max bytes remaining
}
```

### func (\*LimitedReader) Read 

```go
func (l *LimitedReader) Read(p []byte) (n int, err error)
```

type OffsetWriter 
--------------------------------------------------

An OffsetWriter maps writes at offset base to offset base+off in the
underlying writer.

```go
type OffsetWriter struct {
    // contains filtered or unexported fields
}
```

### func NewOffsetWriter 

```go
func NewOffsetWriter(w WriterAt, off int64) *OffsetWriter
```

NewOffsetWriter returns an OffsetWriter that writes to w starting at
offset off.

### func (\*OffsetWriter) Seek 

```go
func (o *OffsetWriter) Seek(offset int64, whence int) (int64, error)
```

### func (\*OffsetWriter) Write 

```go
func (o *OffsetWriter) Write(p []byte) (n int, err error)
```

### func (\*OffsetWriter) WriteAt 

```go
func (o *OffsetWriter) WriteAt(p []byte, off int64) (n int, err error)
```

type PipeReader 
---------------

A PipeReader is the read half of a pipe.

```go
type PipeReader struct {
    // contains filtered or unexported fields
}
```

### func (\*PipeReader) Close 

```go
func (r *PipeReader) Close() error
```

Close closes the reader; subsequent writes to the write half of the pipe
will return the error ErrClosedPipe.

### func (\*PipeReader) CloseWithError 

```go
func (r *PipeReader) CloseWithError(err error) error
```

CloseWithError closes the reader; subsequent writes to the write half of
the pipe will return the error err.

CloseWithError never overwrites the previous error if it exists and
always returns nil.

### func (\*PipeReader) Read 

```go
func (r *PipeReader) Read(data []byte) (n int, err error)
```

Read implements the standard Read interface: it reads data from the
pipe, blocking until a writer arrives or the write end is closed. If the
write end is closed with an error, that error is returned as err;
otherwise err is EOF.

type PipeWriter 
---------------

A PipeWriter is the write half of a pipe.

```go
type PipeWriter struct {
    // contains filtered or unexported fields
}
```

### func (\*PipeWriter) Close 

```go
func (w *PipeWriter) Close() error
```

Close closes the writer; subsequent reads from the read half of the pipe
will return no bytes and EOF.

### func (\*PipeWriter) CloseWithError 

```go
func (w *PipeWriter) CloseWithError(err error) error
```

CloseWithError closes the writer; subsequent reads from the read half of
the pipe will return no bytes and the error err, or EOF if err is nil.

CloseWithError never overwrites the previous error if it exists and
always returns nil.

### func (\*PipeWriter) Write 

```go
func (w *PipeWriter) Write(data []byte) (n int, err error)
```

Write implements the standard Write interface: it writes data to the
pipe, blocking until one or more readers have consumed all the data or
the read end is closed. If the read end is closed with an error, that
err is returned as err; otherwise err is ErrClosedPipe.

type ReadCloser 
---------------

ReadCloser is the interface that groups the basic Read and Close
methods.

```go
type ReadCloser interface {
    Reader
    Closer
}
```

### func NopCloser 

```go
func NopCloser(r Reader) ReadCloser
```

NopCloser returns a ReadCloser with a no-op Close method wrapping the
provided Reader r. If r implements WriterTo, the returned ReadCloser
will implement WriterTo by forwarding calls to r.

type ReadSeekCloser 
----------------------------------------------------

ReadSeekCloser is the interface that groups the basic Read, Seek and
Close methods.

```go
type ReadSeekCloser interface {
    Reader
    Seeker
    Closer
}
```

type ReadSeeker 
---------------

ReadSeeker is the interface that groups the basic Read and Seek methods.

```go
type ReadSeeker interface {
    Reader
    Seeker
}
```

type ReadWriteCloser 
--------------------

ReadWriteCloser is the interface that groups the basic Read, Write and
Close methods.

```go
type ReadWriteCloser interface {
    Reader
    Writer
    Closer
}
```

type ReadWriteSeeker 
--------------------

ReadWriteSeeker is the interface that groups the basic Read, Write and
Seek methods.

```go
type ReadWriteSeeker interface {
    Reader
    Writer
    Seeker
}
```

type ReadWriter 
---------------

ReadWriter is the interface that groups the basic Read and Write
methods.

```go
type ReadWriter interface {
    Reader
    Writer
}
```

type Reader 
-----------

Reader is the interface that wraps the basic Read method.

Read reads up to len(p) bytes into p. It returns the number of bytes
read (0 \<= n \<= len(p)) and any error encountered. Even if Read
returns n \< len(p), it may use all of p as scratch space during the
call. If some data is available but not len(p) bytes, Read
conventionally returns what is available instead of waiting for more.

When Read encounters an error or end-of-file condition after
successfully reading n \> 0 bytes, it returns the number of bytes read.
It may return the (non-nil) error from the same call or return the error
(and n == 0) from a subsequent call. An instance of this general case is
that a Reader returning a non-zero number of bytes at the end of the
input stream may return either err == EOF or err == nil. The next Read
should return 0, EOF.

Callers should always process the n \> 0 bytes returned before
considering the error err. Doing so correctly handles I/O errors that
happen after reading some bytes and also both of the allowed EOF
behaviors.

If len(p) == 0, Read should always return n == 0. It may return a
non-nil error if some error condition is known, such as EOF.

Implementations of Read are discouraged from returning a zero byte count
with a nil error, except when len(p) == 0. Callers should treat a return
of 0 and nil as indicating that nothing happened; in particular it does
not indicate EOF.

Implementations must not retain p.

```go
type Reader interface {
    Read(p []byte) (n int, err error)
}
```

### func LimitReader 

```go
func LimitReader(r Reader, n int64) Reader
```

LimitReader returns a Reader that reads from r but stops with EOF after
n bytes. The underlying implementation is a \*LimitedReader.

#### [Example]

Code:

```go
r := strings.NewReader("some io.Reader stream to be read\n")
lr := io.LimitReader(r, 4)

if _, err := io.Copy(os.Stdout, lr); err != nil {
    log.Fatal(err)
}
```

Output:

```go
some
```

### func MultiReader 

```go
func MultiReader(readers ...Reader) Reader
```

MultiReader returns a Reader that\'s the logical concatenation of the
provided input readers. They\'re read sequentially. Once all inputs have
returned EOF, Read will return EOF. If any of the readers return a
non-nil, non-EOF error, Read will return that error.

#### [Example]

Code:

```go
r1 := strings.NewReader("first reader ")
r2 := strings.NewReader("second reader ")
r3 := strings.NewReader("third reader\n")
r := io.MultiReader(r1, r2, r3)

if _, err := io.Copy(os.Stdout, r); err != nil {
    log.Fatal(err)
}
```

Output:

```go
first reader second reader third reader
```

### func TeeReader 

```go
func TeeReader(r Reader, w Writer) Reader
```

TeeReader returns a Reader that writes to w what it reads from r. All
reads from r performed through it are matched with corresponding writes
to w. There is no internal buffering - the write must complete before
the read completes. Any error encountered while writing is reported as a
read error.

#### [Example]

Code:

```go
var r io.Reader = strings.NewReader("some io.Reader stream to be read\n")

r = io.TeeReader(r, os.Stdout)

// Everything read from r will be copied to stdout.
if _, err := io.ReadAll(r); err != nil {
    log.Fatal(err)
}
```

Output:

```go
some io.Reader stream to be read
```

type ReaderAt 
-------------

ReaderAt is the interface that wraps the basic ReadAt method.

ReadAt reads len(p) bytes into p starting at offset off in the
underlying input source. It returns the number of bytes read (0 \<= n
\<= len(p)) and any error encountered.

When ReadAt returns n \< len(p), it returns a non-nil error explaining
why more bytes were not returned. In this respect, ReadAt is stricter
than Read.

Even if ReadAt returns n \< len(p), it may use all of p as scratch space
during the call. If some data is available but not len(p) bytes, ReadAt
blocks until either all the data is available or an error occurs. In
this respect ReadAt is different from Read.

If the n = len(p) bytes returned by ReadAt are at the end of the input
source, ReadAt may return either err == EOF or err == nil.

If ReadAt is reading from an input source with a seek offset, ReadAt
should not affect nor be affected by the underlying seek offset.

Clients of ReadAt can execute parallel ReadAt calls on the same input
source.

Implementations must not retain p.

```go
type ReaderAt interface {
    ReadAt(p []byte, off int64) (n int, err error)
}
```

type ReaderFrom 
---------------

ReaderFrom is the interface that wraps the ReadFrom method.

ReadFrom reads data from r until EOF or error. The return value n is the
number of bytes read. Any error except EOF encountered during the read
is also returned.

The Copy function uses ReaderFrom if available.

```go
type ReaderFrom interface {
    ReadFrom(r Reader) (n int64, err error)
}
```

type RuneReader 
---------------

RuneReader is the interface that wraps the ReadRune method.

ReadRune reads a single encoded Unicode character and returns the rune
and its size in bytes. If no character is available, err will be set.

```go
type RuneReader interface {
    ReadRune() (r rune, size int, err error)
}
```

type RuneScanner 
----------------

RuneScanner is the interface that adds the UnreadRune method to the
basic ReadRune method.

UnreadRune causes the next call to ReadRune to return the last rune
read. If the last operation was not a successful call to ReadRune,
UnreadRune may return an error, unread the last rune read (or the rune
prior to the last-unread rune), or (in implementations that support the
Seeker interface) seek to the start of the rune before the current
offset.

```go
type RuneScanner interface {
    RuneReader
    UnreadRune() error
}
```

type SectionReader 
------------------

SectionReader implements Read, Seek, and ReadAt on a section of an
underlying ReaderAt.

```go
type SectionReader struct {
    // contains filtered or unexported fields
}
```

#### [Example]

Code:

```go
r := strings.NewReader("some io.Reader stream to be read\n")
s := io.NewSectionReader(r, 5, 17)

if _, err := io.Copy(os.Stdout, s); err != nil {
    log.Fatal(err)
}
```

Output:

```go
io.Reader stream
```

### func NewSectionReader 

```go
func NewSectionReader(r ReaderAt, off int64, n int64) *SectionReader
```

NewSectionReader returns a SectionReader that reads from r starting at
offset off and stops with EOF after n bytes.

### func (\*SectionReader) Read 

```go
func (s *SectionReader) Read(p []byte) (n int, err error)
```

#### [Example]

Code:

```go
r := strings.NewReader("some io.Reader stream to be read\n")
s := io.NewSectionReader(r, 5, 17)

buf := make([]byte, 9)
if _, err := s.Read(buf); err != nil {
    log.Fatal(err)
}

fmt.Printf("%s\n", buf)
```

Output:

```go
io.Reader
```

### func (\*SectionReader) ReadAt 

```go
func (s *SectionReader) ReadAt(p []byte, off int64) (n int, err error)
```

#### [Example]

Code:

```go
r := strings.NewReader("some io.Reader stream to be read\n")
s := io.NewSectionReader(r, 5, 17)

buf := make([]byte, 6)
if _, err := s.ReadAt(buf, 10); err != nil {
    log.Fatal(err)
}

fmt.Printf("%s\n", buf)
```

Output:

```go
stream
```

### func (\*SectionReader) Seek 

```go
func (s *SectionReader) Seek(offset int64, whence int) (int64, error)
```

#### [Example]

Code:

```go
r := strings.NewReader("some io.Reader stream to be read\n")
s := io.NewSectionReader(r, 5, 17)

if _, err := s.Seek(10, io.SeekStart); err != nil {
    log.Fatal(err)
}

if _, err := io.Copy(os.Stdout, s); err != nil {
    log.Fatal(err)
}
```

Output:

```go
stream
```

### func (\*SectionReader) Size 

```go
func (s *SectionReader) Size() int64
```

Size returns the size of the section in bytes.

#### [Example]

Code:

```go
r := strings.NewReader("some io.Reader stream to be read\n")
s := io.NewSectionReader(r, 5, 17)

fmt.Println(s.Size())
```

Output:

```go
17
```

type Seeker 
-----------

Seeker is the interface that wraps the basic Seek method.

Seek sets the offset for the next Read or Write to offset, interpreted
according to whence: SeekStart means relative to the start of the file,
SeekCurrent means relative to the current offset, and SeekEnd means
relative to the end (for example, offset = -2 specifies the penultimate
byte of the file). Seek returns the new offset relative to the start of
the file or an error, if any.

Seeking to an offset before the start of the file is an error. Seeking
to any positive offset may be allowed, but if the new offset exceeds the
size of the underlying object the behavior of subsequent I/O operations
is implementation-dependent.

```go
type Seeker interface {
    Seek(offset int64, whence int) (int64, error)
}
```

type StringWriter 
--------------------------------------------------

StringWriter is the interface that wraps the WriteString method.

```go
type StringWriter interface {
    WriteString(s string) (n int, err error)
}
```

type WriteCloser 
----------------

WriteCloser is the interface that groups the basic Write and Close
methods.

```go
type WriteCloser interface {
    Writer
    Closer
}
```

type WriteSeeker 
----------------

WriteSeeker is the interface that groups the basic Write and Seek
methods.

```go
type WriteSeeker interface {
    Writer
    Seeker
}
```

type Writer 
-----------

Writer is the interface that wraps the basic Write method.

Write writes len(p) bytes from p to the underlying data stream. It
returns the number of bytes written from p (0 \<= n \<= len(p)) and any
error encountered that caused the write to stop early. Write must return
a non-nil error if it returns n \< len(p). Write must not modify the
slice data, even temporarily.

Implementations must not retain p.

```go
type Writer interface {
    Write(p []byte) (n int, err error)
}
```

Discard is a Writer on which all Write calls succeed without doing
anything.

```go
var Discard Writer = discard{}
```

### func MultiWriter 

```go
func MultiWriter(writers ...Writer) Writer
```

MultiWriter creates a writer that duplicates its writes to all the
provided writers, similar to the Unix tee(1) command.

Each write is written to each listed writer, one at a time. If a listed
writer returns an error, that overall write operation stops and returns
the error; it does not continue down the list.

#### [Example]

Code:

```go
r := strings.NewReader("some io.Reader stream to be read\n")

var buf1, buf2 strings.Builder
w := io.MultiWriter(&buf1, &buf2)

if _, err := io.Copy(w, r); err != nil {
    log.Fatal(err)
}

fmt.Print(buf1.String())
fmt.Print(buf2.String())
```

Output:

```go
some io.Reader stream to be read
some io.Reader stream to be read
```

type WriterAt 
-------------

WriterAt is the interface that wraps the basic WriteAt method.

WriteAt writes len(p) bytes from p to the underlying data stream at
offset off. It returns the number of bytes written from p (0 \<= n \<=
len(p)) and any error encountered that caused the write to stop early.
WriteAt must return a non-nil error if it returns n \< len(p).

If WriteAt is writing to a destination with a seek offset, WriteAt
should not affect nor be affected by the underlying seek offset.

Clients of WriteAt can execute parallel WriteAt calls on the same
destination if the ranges do not overlap.

Implementations must not retain p.

```go
type WriterAt interface {
    WriteAt(p []byte, off int64) (n int, err error)
}
```

type WriterTo 
-------------

WriterTo is the interface that wraps the WriteTo method.

WriteTo writes data to w until there\'s no more data to write or when an
error occurs. The return value n is the number of bytes written. Any
error encountered during the write is also returned.

The Copy function uses WriterTo if available.

```go
type WriterTo interface {
    WriteTo(w Writer) (n int64, err error)
}
```

Subdirectories 
--------------

 
Name


Synopsis

[..](../index)

[fs](fs/index)

Package fs defines basic interfaces to a file system.

[ioutil](ioutil/index)

Package ioutil implements some I/O utility functions.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/io/>

