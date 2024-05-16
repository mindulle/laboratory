Package macho
=============

-   `import "debug/macho"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package macho implements access to Mach-O object files.

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
-   [type Cpu](#Cpu)
-   [func (i Cpu) GoString() string](#Cpu.GoString)
-   [func (i Cpu) String() string](#Cpu.String)
-   [type Dylib](#Dylib)
-   [type DylibCmd](#DylibCmd)
-   [type Dysymtab](#Dysymtab)
-   [type DysymtabCmd](#DysymtabCmd)
-   [type FatArch](#FatArch)
-   [type FatArchHeader](#FatArchHeader)
-   [type FatFile](#FatFile)
-   [func NewFatFile(r io.ReaderAt) (\*FatFile, error)](#NewFatFile)
-   [func OpenFat(name string) (\*FatFile, error)](#OpenFat)
-   [func (ff \*FatFile) Close() error](#FatFile.Close)
-   [type File](#File)
-   [func NewFile(r io.ReaderAt) (\*File, error)](#NewFile)
-   [func Open(name string) (\*File, error)](#Open)
-   [func (f \*File) Close() error](#File.Close)
-   [func (f \*File) DWARF() (\*dwarf.Data, error)](#File.DWARF)
-   [func (f \*File) ImportedLibraries() (\[\]string,
    error)](#File.ImportedLibraries)
-   [func (f \*File) ImportedSymbols() (\[\]string,
    error)](#File.ImportedSymbols)
-   [func (f \*File) Section(name string) \*Section](#File.Section)
-   [func (f \*File) Segment(name string) \*Segment](#File.Segment)
-   [type FileHeader](#FileHeader)
-   [type FormatError](#FormatError)
-   [func (e \*FormatError) Error() string](#FormatError.Error)
-   [type Load](#Load)
-   [type LoadBytes](#LoadBytes)
-   [func (b LoadBytes) Raw() \[\]byte](#LoadBytes.Raw)
-   [type LoadCmd](#LoadCmd)
-   [func (i LoadCmd) GoString() string](#LoadCmd.GoString)
-   [func (i LoadCmd) String() string](#LoadCmd.String)
-   [type Nlist32](#Nlist32)
-   [type Nlist64](#Nlist64)
-   [type Regs386](#Regs386)
-   [type RegsAMD64](#RegsAMD64)
-   [type Reloc](#Reloc)
-   [type RelocTypeARM](#RelocTypeARM)
-   [func (r RelocTypeARM) GoString() string](#RelocTypeARM.GoString)
-   [func (i RelocTypeARM) String() string](#RelocTypeARM.String)
-   [type RelocTypeARM64](#RelocTypeARM64)
-   [func (r RelocTypeARM64) GoString()
    string](#RelocTypeARM64.GoString)
-   [func (i RelocTypeARM64) String() string](#RelocTypeARM64.String)
-   [type RelocTypeGeneric](#RelocTypeGeneric)
-   [func (r RelocTypeGeneric) GoString()
    string](#RelocTypeGeneric.GoString)
-   [func (i RelocTypeGeneric) String()
    string](#RelocTypeGeneric.String)
-   [type RelocTypeX86\_64](#RelocTypeX86_64)
-   [func (r RelocTypeX86\_64) GoString()
    string](#RelocTypeX86_64.GoString)
-   [func (i RelocTypeX86\_64) String() string](#RelocTypeX86_64.String)
-   [type Rpath](#Rpath)
-   [type RpathCmd](#RpathCmd)
-   [type Section](#Section)
-   [func (s \*Section) Data() (\[\]byte, error)](#Section.Data)
-   [func (s \*Section) Open() io.ReadSeeker](#Section.Open)
-   [type Section32](#Section32)
-   [type Section64](#Section64)
-   [type SectionHeader](#SectionHeader)
-   [type Segment](#Segment)
-   [func (s \*Segment) Data() (\[\]byte, error)](#Segment.Data)
-   [func (s \*Segment) Open() io.ReadSeeker](#Segment.Open)
-   [type Segment32](#Segment32)
-   [type Segment64](#Segment64)
-   [type SegmentHeader](#SegmentHeader)
-   [type Symbol](#Symbol)
-   [type Symtab](#Symtab)
-   [type SymtabCmd](#SymtabCmd)
-   [type Thread](#Thread)
-   [type Type](#Type)
-   [func (t Type) GoString() string](#Type.GoString)
-   [func (t Type) String() string](#Type.String)

### Package files

fat.go file.go macho.go reloctype.go reloctype\_string.go

Constants 
---------

```go
const (
    Magic32  uint32 = 0xfeedface
    Magic64  uint32 = 0xfeedfacf
    MagicFat uint32 = 0xcafebabe
)
```

```go
const (
    FlagNoUndefs              uint32 = 0x1
    FlagIncrLink              uint32 = 0x2
    FlagDyldLink              uint32 = 0x4
    FlagBindAtLoad            uint32 = 0x8
    FlagPrebound              uint32 = 0x10
    FlagSplitSegs             uint32 = 0x20
    FlagLazyInit              uint32 = 0x40
    FlagTwoLevel              uint32 = 0x80
    FlagForceFlat             uint32 = 0x100
    FlagNoMultiDefs           uint32 = 0x200
    FlagNoFixPrebinding       uint32 = 0x400
    FlagPrebindable           uint32 = 0x800
    FlagAllModsBound          uint32 = 0x1000
    FlagSubsectionsViaSymbols uint32 = 0x2000
    FlagCanonical             uint32 = 0x4000
    FlagWeakDefines           uint32 = 0x8000
    FlagBindsToWeak           uint32 = 0x10000
    FlagAllowStackExecution   uint32 = 0x20000
    FlagRootSafe              uint32 = 0x40000
    FlagSetuidSafe            uint32 = 0x80000
    FlagNoReexportedDylibs    uint32 = 0x100000
    FlagPIE                   uint32 = 0x200000
    FlagDeadStrippableDylib   uint32 = 0x400000
    FlagHasTLVDescriptors     uint32 = 0x800000
    FlagNoHeapExecution       uint32 = 0x1000000
    FlagAppExtensionSafe      uint32 = 0x2000000
)
```

Variables 
---------

ErrNotFat is returned from NewFatFile or OpenFat when the file is not a
universal binary but may be a thin binary, based on its magic number.

```go
var ErrNotFat = &FormatError{0, "not a fat Mach-O file", nil}
```

type Cpu 
--------

A Cpu is a Mach-O cpu type.

```go
type Cpu uint32
```

```go
const (
    Cpu386   Cpu = 7
    CpuAmd64 Cpu = Cpu386 | cpuArch64
    CpuArm   Cpu = 12
    CpuArm64 Cpu = CpuArm | cpuArch64
    CpuPpc   Cpu = 18
    CpuPpc64 Cpu = CpuPpc | cpuArch64
)
```

### func (Cpu) GoString 

```go
func (i Cpu) GoString() string
```

### func (Cpu) String 

```go
func (i Cpu) String() string
```

type Dylib 
----------

A Dylib represents a Mach-O load dynamic library command.

```go
type Dylib struct {
    LoadBytes
    Name           string
    Time           uint32
    CurrentVersion uint32
    CompatVersion  uint32
}
```

type DylibCmd 
-------------

A DylibCmd is a Mach-O load dynamic library command.

```go
type DylibCmd struct {
    Cmd            LoadCmd
    Len            uint32
    Name           uint32
    Time           uint32
    CurrentVersion uint32
    CompatVersion  uint32
}
```

type Dysymtab 
-------------

A Dysymtab represents a Mach-O dynamic symbol table command.

```go
type Dysymtab struct {
    LoadBytes
    DysymtabCmd
    IndirectSyms []uint32 // indices into Symtab.Syms
}
```

type DysymtabCmd 
----------------

A DysymtabCmd is a Mach-O dynamic symbol table command.

```go
type DysymtabCmd struct {
    Cmd            LoadCmd
    Len            uint32
    Ilocalsym      uint32
    Nlocalsym      uint32
    Iextdefsym     uint32
    Nextdefsym     uint32
    Iundefsym      uint32
    Nundefsym      uint32
    Tocoffset      uint32
    Ntoc           uint32
    Modtaboff      uint32
    Nmodtab        uint32
    Extrefsymoff   uint32
    Nextrefsyms    uint32
    Indirectsymoff uint32
    Nindirectsyms  uint32
    Extreloff      uint32
    Nextrel        uint32
    Locreloff      uint32
    Nlocrel        uint32
}
```

type FatArch 
-------------------------------------------

A FatArch is a Mach-O File inside a FatFile.

```go
type FatArch struct {
    FatArchHeader
    *File
}
```

type FatArchHeader 
-------------------------------------------------

A FatArchHeader represents a fat header for a specific image
architecture.

```go
type FatArchHeader struct {
    Cpu    Cpu
    SubCpu uint32
    Offset uint32
    Size   uint32
    Align  uint32
}
```

type FatFile 
-------------------------------------------

A FatFile is a Mach-O universal binary that contains at least one
architecture.

```go
type FatFile struct {
    Magic  uint32
    Arches []FatArch
    // contains filtered or unexported fields
}
```

### func NewFatFile 

```go
func NewFatFile(r io.ReaderAt) (*FatFile, error)
```

NewFatFile creates a new FatFile for accessing all the Mach-O images in
a universal binary. The Mach-O binary is expected to start at position 0
in the ReaderAt.

### func OpenFat 

```go
func OpenFat(name string) (*FatFile, error)
```

OpenFat opens the named file using os.Open and prepares it for use as a
Mach-O universal binary.

### func (\*FatFile) Close 

```go
func (ff *FatFile) Close() error
```

type File 
---------

A File represents an open Mach-O file.

```go
type File struct {
    FileHeader
    ByteOrder binary.ByteOrder
    Loads     []Load
    Sections  []*Section

    Symtab   *Symtab
    Dysymtab *Dysymtab
    // contains filtered or unexported fields
}
```

### func NewFile 

```go
func NewFile(r io.ReaderAt) (*File, error)
```

NewFile creates a new File for accessing a Mach-O binary in an
underlying reader. The Mach-O binary is expected to start at position 0
in the ReaderAt.

### func Open 

```go
func Open(name string) (*File, error)
```

Open opens the named file using os.Open and prepares it for use as a
Mach-O binary.

### func (\*File) Close 

```go
func (f *File) Close() error
```

Close closes the File. If the File was created using NewFile directly
instead of Open, Close has no effect.

### func (\*File) DWARF 

```go
func (f *File) DWARF() (*dwarf.Data, error)
```

DWARF returns the DWARF debug information for the Mach-O file.

### func (\*File) ImportedLibraries 

```go
func (f *File) ImportedLibraries() ([]string, error)
```

ImportedLibraries returns the paths of all libraries referred to by the
binary f that are expected to be linked with the binary at dynamic link
time.

### func (\*File) ImportedSymbols 

```go
func (f *File) ImportedSymbols() ([]string, error)
```

ImportedSymbols returns the names of all symbols referred to by the
binary f that are expected to be satisfied by other libraries at dynamic
load time.

### func (\*File) Section 

```go
func (f *File) Section(name string) *Section
```

Section returns the first section with the given name, or nil if no such
section exists.

### func (\*File) Segment 

```go
func (f *File) Segment(name string) *Segment
```

Segment returns the first Segment with the given name, or nil if no such
segment exists.

type FileHeader 
---------------

A FileHeader represents a Mach-O file header.

```go
type FileHeader struct {
    Magic  uint32
    Cpu    Cpu
    SubCpu uint32
    Type   Type
    Ncmd   uint32
    Cmdsz  uint32
    Flags  uint32
}
```

type FormatError 
----------------

FormatError is returned by some operations if the data does not have the
correct format for an object file.

```go
type FormatError struct {
    // contains filtered or unexported fields
}
```

### func (\*FormatError) Error 

```go
func (e *FormatError) Error() string
```

type Load 
---------

A Load represents any Mach-O load command.

```go
type Load interface {
    Raw() []byte
}
```

type LoadBytes 
--------------

A LoadBytes is the uninterpreted bytes of a Mach-O load command.

```go
type LoadBytes []byte
```

### func (LoadBytes) Raw 

```go
func (b LoadBytes) Raw() []byte
```

type LoadCmd 
------------

A LoadCmd is a Mach-O load command.

```go
type LoadCmd uint32
```

```go
const (
    LoadCmdSegment    LoadCmd = 0x1
    LoadCmdSymtab     LoadCmd = 0x2
    LoadCmdThread     LoadCmd = 0x4
    LoadCmdUnixThread LoadCmd = 0x5 // thread+stack
    LoadCmdDysymtab   LoadCmd = 0xb
    LoadCmdDylib      LoadCmd = 0xc // load dylib command
    LoadCmdDylinker   LoadCmd = 0xf // id dylinker command (not load dylinker command)
    LoadCmdSegment64  LoadCmd = 0x19
    LoadCmdRpath      LoadCmd = 0x8000001c
)
```

### func (LoadCmd) GoString 

```go
func (i LoadCmd) GoString() string
```

### func (LoadCmd) String 

```go
func (i LoadCmd) String() string
```

type Nlist32 
------------

An Nlist32 is a Mach-O 32-bit symbol table entry.

```go
type Nlist32 struct {
    Name  uint32
    Type  uint8
    Sect  uint8
    Desc  uint16
    Value uint32
}
```

type Nlist64 
------------

An Nlist64 is a Mach-O 64-bit symbol table entry.

```go
type Nlist64 struct {
    Name  uint32
    Type  uint8
    Sect  uint8
    Desc  uint16
    Value uint64
}
```

type Regs386 
------------

Regs386 is the Mach-O 386 register structure.

```go
type Regs386 struct {
    AX    uint32
    BX    uint32
    CX    uint32
    DX    uint32
    DI    uint32
    SI    uint32
    BP    uint32
    SP    uint32
    SS    uint32
    FLAGS uint32
    IP    uint32
    CS    uint32
    DS    uint32
    ES    uint32
    FS    uint32
    GS    uint32
}
```

type RegsAMD64 
--------------

RegsAMD64 is the Mach-O AMD64 register structure.

```go
type RegsAMD64 struct {
    AX    uint64
    BX    uint64
    CX    uint64
    DX    uint64
    DI    uint64
    SI    uint64
    BP    uint64
    SP    uint64
    R8    uint64
    R9    uint64
    R10   uint64
    R11   uint64
    R12   uint64
    R13   uint64
    R14   uint64
    R15   uint64
    IP    uint64
    FLAGS uint64
    CS    uint64
    FS    uint64
    GS    uint64
}
```

type Reloc 
-------------------------------------------

A Reloc represents a Mach-O relocation.

```go
type Reloc struct {
    Addr  uint32
    Value uint32
    // when Scattered == false && Extern == true, Value is the symbol number.
    // when Scattered == false && Extern == false, Value is the section number.
    // when Scattered == true, Value is the value that this reloc refers to.
    Type      uint8
    Len       uint8 // 0=byte, 1=word, 2=long, 3=quad
    Pcrel     bool
    Extern    bool // valid if Scattered == false
    Scattered bool
}
```

type RelocTypeARM 
--------------------------------------------------

```go
type RelocTypeARM int
```

```go
const (
    ARM_RELOC_VANILLA        RelocTypeARM = 0
    ARM_RELOC_PAIR           RelocTypeARM = 1
    ARM_RELOC_SECTDIFF       RelocTypeARM = 2
    ARM_RELOC_LOCAL_SECTDIFF RelocTypeARM = 3
    ARM_RELOC_PB_LA_PTR      RelocTypeARM = 4
    ARM_RELOC_BR24           RelocTypeARM = 5
    ARM_THUMB_RELOC_BR22     RelocTypeARM = 6
    ARM_THUMB_32BIT_BRANCH   RelocTypeARM = 7
    ARM_RELOC_HALF           RelocTypeARM = 8
    ARM_RELOC_HALF_SECTDIFF  RelocTypeARM = 9
)
```

### func (RelocTypeARM) GoString 

```go
func (r RelocTypeARM) GoString() string
```

### func (RelocTypeARM) String 

```go
func (i RelocTypeARM) String() string
```

type RelocTypeARM64 
----------------------------------------------------

```go
type RelocTypeARM64 int
```

```go
const (
    ARM64_RELOC_UNSIGNED            RelocTypeARM64 = 0
    ARM64_RELOC_SUBTRACTOR          RelocTypeARM64 = 1
    ARM64_RELOC_BRANCH26            RelocTypeARM64 = 2
    ARM64_RELOC_PAGE21              RelocTypeARM64 = 3
    ARM64_RELOC_PAGEOFF12           RelocTypeARM64 = 4
    ARM64_RELOC_GOT_LOAD_PAGE21     RelocTypeARM64 = 5
    ARM64_RELOC_GOT_LOAD_PAGEOFF12  RelocTypeARM64 = 6
    ARM64_RELOC_POINTER_TO_GOT      RelocTypeARM64 = 7
    ARM64_RELOC_TLVP_LOAD_PAGE21    RelocTypeARM64 = 8
    ARM64_RELOC_TLVP_LOAD_PAGEOFF12 RelocTypeARM64 = 9
    ARM64_RELOC_ADDEND              RelocTypeARM64 = 10
)
```

### func (RelocTypeARM64) GoString 

```go
func (r RelocTypeARM64) GoString() string
```

### func (RelocTypeARM64) String 

```go
func (i RelocTypeARM64) String() string
```

type RelocTypeGeneric 
------------------------------------------------------

```go
type RelocTypeGeneric int
```

```go
const (
    GENERIC_RELOC_VANILLA        RelocTypeGeneric = 0
    GENERIC_RELOC_PAIR           RelocTypeGeneric = 1
    GENERIC_RELOC_SECTDIFF       RelocTypeGeneric = 2
    GENERIC_RELOC_PB_LA_PTR      RelocTypeGeneric = 3
    GENERIC_RELOC_LOCAL_SECTDIFF RelocTypeGeneric = 4
    GENERIC_RELOC_TLV            RelocTypeGeneric = 5
)
```

### func (RelocTypeGeneric) GoString 

```go
func (r RelocTypeGeneric) GoString() string
```

### func (RelocTypeGeneric) String 

```go
func (i RelocTypeGeneric) String() string
```

type RelocTypeX86\_64 
------------------------------------------------------

```go
type RelocTypeX86_64 int
```

```go
const (
    X86_64_RELOC_UNSIGNED   RelocTypeX86_64 = 0
    X86_64_RELOC_SIGNED     RelocTypeX86_64 = 1
    X86_64_RELOC_BRANCH     RelocTypeX86_64 = 2
    X86_64_RELOC_GOT_LOAD   RelocTypeX86_64 = 3
    X86_64_RELOC_GOT        RelocTypeX86_64 = 4
    X86_64_RELOC_SUBTRACTOR RelocTypeX86_64 = 5
    X86_64_RELOC_SIGNED_1   RelocTypeX86_64 = 6
    X86_64_RELOC_SIGNED_2   RelocTypeX86_64 = 7
    X86_64_RELOC_SIGNED_4   RelocTypeX86_64 = 8
    X86_64_RELOC_TLV        RelocTypeX86_64 = 9
)
```

### func (RelocTypeX86\_64) GoString 

```go
func (r RelocTypeX86_64) GoString() string
```

### func (RelocTypeX86\_64) String 

```go
func (i RelocTypeX86_64) String() string
```

type Rpath 
-------------------------------------------

A Rpath represents a Mach-O rpath command.

```go
type Rpath struct {
    LoadBytes
    Path string
}
```

type RpathCmd 
----------------------------------------------

A RpathCmd is a Mach-O rpath command.

```go
type RpathCmd struct {
    Cmd  LoadCmd
    Len  uint32
    Path uint32
}
```

type Section 
------------

```go
type Section struct {
    SectionHeader
    Relocs []Reloc // Go 1.10

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

Data reads and returns the contents of the Mach-O section.

### func (\*Section) Open 

```go
func (s *Section) Open() io.ReadSeeker
```

Open returns a new ReadSeeker reading the Mach-O section.

type Section32 
--------------

A Section32 is a 32-bit Mach-O section header.

```go
type Section32 struct {
    Name     [16]byte
    Seg      [16]byte
    Addr     uint32
    Size     uint32
    Offset   uint32
    Align    uint32
    Reloff   uint32
    Nreloc   uint32
    Flags    uint32
    Reserve1 uint32
    Reserve2 uint32
}
```

type Section64 
--------------

A Section64 is a 64-bit Mach-O section header.

```go
type Section64 struct {
    Name     [16]byte
    Seg      [16]byte
    Addr     uint64
    Size     uint64
    Offset   uint32
    Align    uint32
    Reloff   uint32
    Nreloc   uint32
    Flags    uint32
    Reserve1 uint32
    Reserve2 uint32
    Reserve3 uint32
}
```

type SectionHeader 
------------------

```go
type SectionHeader struct {
    Name   string
    Seg    string
    Addr   uint64
    Size   uint64
    Offset uint32
    Align  uint32
    Reloff uint32
    Nreloc uint32
    Flags  uint32
}
```

type Segment 
------------

A Segment represents a Mach-O 32-bit or 64-bit load segment command.

```go
type Segment struct {
    LoadBytes
    SegmentHeader

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

### func (\*Segment) Data 

```go
func (s *Segment) Data() ([]byte, error)
```

Data reads and returns the contents of the segment.

### func (\*Segment) Open 

```go
func (s *Segment) Open() io.ReadSeeker
```

Open returns a new ReadSeeker reading the segment.

type Segment32 
--------------

A Segment32 is a 32-bit Mach-O segment load command.

```go
type Segment32 struct {
    Cmd     LoadCmd
    Len     uint32
    Name    [16]byte
    Addr    uint32
    Memsz   uint32
    Offset  uint32
    Filesz  uint32
    Maxprot uint32
    Prot    uint32
    Nsect   uint32
    Flag    uint32
}
```

type Segment64 
--------------

A Segment64 is a 64-bit Mach-O segment load command.

```go
type Segment64 struct {
    Cmd     LoadCmd
    Len     uint32
    Name    [16]byte
    Addr    uint64
    Memsz   uint64
    Offset  uint64
    Filesz  uint64
    Maxprot uint32
    Prot    uint32
    Nsect   uint32
    Flag    uint32
}
```

type SegmentHeader 
------------------

A SegmentHeader is the header for a Mach-O 32-bit or 64-bit load segment
command.

```go
type SegmentHeader struct {
    Cmd     LoadCmd
    Len     uint32
    Name    string
    Addr    uint64
    Memsz   uint64
    Offset  uint64
    Filesz  uint64
    Maxprot uint32
    Prot    uint32
    Nsect   uint32
    Flag    uint32
}
```

type Symbol 
-----------

A Symbol is a Mach-O 32-bit or 64-bit symbol table entry.

```go
type Symbol struct {
    Name  string
    Type  uint8
    Sect  uint8
    Desc  uint16
    Value uint64
}
```

type Symtab 
-----------

A Symtab represents a Mach-O symbol table command.

```go
type Symtab struct {
    LoadBytes
    SymtabCmd
    Syms []Symbol
}
```

type SymtabCmd 
--------------

A SymtabCmd is a Mach-O symbol table command.

```go
type SymtabCmd struct {
    Cmd     LoadCmd
    Len     uint32
    Symoff  uint32
    Nsyms   uint32
    Stroff  uint32
    Strsize uint32
}
```

type Thread 
-----------

A Thread is a Mach-O thread state command.

```go
type Thread struct {
    Cmd  LoadCmd
    Len  uint32
    Type uint32
    Data []uint32
}
```

type Type 
---------

A Type is the Mach-O file type, e.g. an object file, executable, or
dynamic library.

```go
type Type uint32
```

```go
const (
    TypeObj    Type = 1
    TypeExec   Type = 2
    TypeDylib  Type = 6
    TypeBundle Type = 8
)
```

### func (Type) GoString 

```go
func (t Type) GoString() string
```

### func (Type) String 

```go
func (t Type) String() string
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/debug/macho/>

