Package plan9obj
================

-   `import "debug/plan9obj"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package plan9obj implements access to Plan 9 a.out object files.

### Security 

This package is not designed to be hardened against adversarial inputs,
and is outside the scope of https://go.dev/security/policy>. In
particular, only basic validation is done when parsing object files. As
such, care should be taken when parsing untrusted inputs, as parsing
malformed files may consume significant resources, or cause panics.

Index 
-----

-   [Constants](#pkg-constants)
-   [Variables](#pkg-variables)
-   [type File](#File)
-   [func NewFile(r io.ReaderAt) (\*File, error)](#NewFile)
-   [func Open(name string) (\*File, error)](#Open)
-   [func (f \*File) Close() error](#File.Close)
-   [func (f \*File) Section(name string) \*Section](#File.Section)
-   [func (f \*File) Symbols() (\[\]Sym, error)](#File.Symbols)
-   [type FileHeader](#FileHeader)
-   [type Section](#Section)
-   [func (s \*Section) Data() (\[\]byte, error)](#Section.Data)
-   [func (s \*Section) Open() io.ReadSeeker](#Section.Open)
-   [type SectionHeader](#SectionHeader)
-   [type Sym](#Sym)

### Package files

file.go plan9obj.go

Constants 
---------

```go
const (
    Magic64 = 0x8000 // 64-bit expanded header

    Magic386   = (4*11+0)*11 + 7
    MagicAMD64 = (4*26+0)*26 + 7 + Magic64
    MagicARM   = (4*20+0)*20 + 7
)
```

Variables 
---------

ErrNoSymbols is returned by File.Symbols if there is no such section in
the File.

```go
var ErrNoSymbols = errors.New("no symbol section")
```

type File 
----------------------------------------

A File represents an open Plan 9 a.out file.

```go
type File struct {
    FileHeader
    Sections []*Section
    // contains filtered or unexported fields
}
```

### func NewFile 

```go
func NewFile(r io.ReaderAt) (*File, error)
```

NewFile creates a new File for accessing a Plan 9 binary in an
underlying reader. The Plan 9 binary is expected to start at position 0
in the ReaderAt.

### func Open 

```go
func Open(name string) (*File, error)
```

Open opens the named file using os.Open and prepares it for use as a
Plan 9 a.out binary.

### func (\*File) Close 

```go
func (f *File) Close() error
```

Close closes the File. If the File was created using NewFile directly
instead of Open, Close has no effect.

### func (\*File) Section 

```go
func (f *File) Section(name string) *Section
```

Section returns a section with the given name, or nil if no such section
exists.

### func (\*File) Symbols 

```go
func (f *File) Symbols() ([]Sym, error)
```

Symbols returns the symbol table for f.

type FileHeader 
----------------------------------------------

A FileHeader represents a Plan 9 a.out file header.

```go
type FileHeader struct {
    Magic       uint32
    Bss         uint32
    Entry       uint64
    PtrSize     int
    LoadAddress uint64 // Go 1.4
    HdrSize     uint64 // Go 1.4
}
```

type Section 
-------------------------------------------

A Section represents a single section in a Plan 9 a.out file.

```go
type Section struct {
    SectionHeader

    // Embed ReaderAt for ReadAt method.
    // Do not embed SectionReader directly
    // to avoid having Read and Seek.
    // If a client wants Read and Seek it must use
    // Open() to avoid fighting over the seek offset
    // with other clients.
    io.ReaderAt
    // contains filtered or unexported fields
}
```

### func (\*Section) Data 

```go
func (s *Section) Data() ([]byte, error)
```

Data reads and returns the contents of the Plan 9 a.out section.

### func (\*Section) Open 

```go
func (s *Section) Open() io.ReadSeeker
```

Open returns a new ReadSeeker reading the Plan 9 a.out section.

type SectionHeader 
-------------------------------------------------

A SectionHeader represents a single Plan 9 a.out section header. This
structure doesn\'t exist on-disk, but eases navigation through the
object file.

```go
type SectionHeader struct {
    Name   string
    Size   uint32
    Offset uint32
}
```

type Sym 
---------------------------------------

A Symbol represents an entry in a Plan 9 a.out symbol table section.

```go
type Sym struct {
    Value uint64
    Type  rune
    Name  string
}
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/debug/plan9obj/>

