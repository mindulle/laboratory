Package pe
==========

-   `import "debug/pe"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package pe implements access to PE (Microsoft Windows Portable
Executable) files.

### Security 

This package is not designed to be hardened against adversarial inputs,
and is outside the scope of https://go.dev/security/policy>. In
particular, only basic validation is done when parsing object files. As
such, care should be taken when parsing untrusted inputs, as parsing
malformed files may consume significant resources, or cause panics.

Index 
-----

-   [Constants](#pkg-constants)
-   [type COFFSymbol](#COFFSymbol)
-   [func (sym \*COFFSymbol) FullName(st StringTable) (string,
    error)](#COFFSymbol.FullName)
-   [type COFFSymbolAuxFormat5](#COFFSymbolAuxFormat5)
-   [type DataDirectory](#DataDirectory)
-   [type File](#File)
-   [func NewFile(r io.ReaderAt) (\*File, error)](#NewFile)
-   [func Open(name string) (\*File, error)](#Open)
-   [func (f \*File) COFFSymbolReadSectionDefAux(idx int)
    (\*COFFSymbolAuxFormat5, error)](#File.COFFSymbolReadSectionDefAux)
-   [func (f \*File) Close() error](#File.Close)
-   [func (f \*File) DWARF() (\*dwarf.Data, error)](#File.DWARF)
-   [func (f \*File) ImportedLibraries() (\[\]string,
    error)](#File.ImportedLibraries)
-   [func (f \*File) ImportedSymbols() (\[\]string,
    error)](#File.ImportedSymbols)
-   [func (f \*File) Section(name string) \*Section](#File.Section)
-   [type FileHeader](#FileHeader)
-   [type FormatError](#FormatError)
-   [func (e \*FormatError) Error() string](#FormatError.Error)
-   [type ImportDirectory](#ImportDirectory)
-   [type OptionalHeader32](#OptionalHeader32)
-   [type OptionalHeader64](#OptionalHeader64)
-   [type Reloc](#Reloc)
-   [type Section](#Section)
-   [func (s \*Section) Data() (\[\]byte, error)](#Section.Data)
-   [func (s \*Section) Open() io.ReadSeeker](#Section.Open)
-   [type SectionHeader](#SectionHeader)
-   [type SectionHeader32](#SectionHeader32)
-   [type StringTable](#StringTable)
-   [func (st StringTable) String(start uint32) (string,
    error)](#StringTable.String)
-   [type Symbol](#Symbol)

### Package files

file.go pe.go section.go string.go symbol.go

Constants 
---------

```go
const (
    IMAGE_FILE_MACHINE_UNKNOWN     = 0x0
    IMAGE_FILE_MACHINE_AM33        = 0x1d3
    IMAGE_FILE_MACHINE_AMD64       = 0x8664
    IMAGE_FILE_MACHINE_ARM         = 0x1c0
    IMAGE_FILE_MACHINE_ARMNT       = 0x1c4
    IMAGE_FILE_MACHINE_ARM64       = 0xaa64
    IMAGE_FILE_MACHINE_EBC         = 0xebc
    IMAGE_FILE_MACHINE_I386        = 0x14c
    IMAGE_FILE_MACHINE_IA64        = 0x200
    IMAGE_FILE_MACHINE_LOONGARCH32 = 0x6232
    IMAGE_FILE_MACHINE_LOONGARCH64 = 0x6264
    IMAGE_FILE_MACHINE_M32R        = 0x9041
    IMAGE_FILE_MACHINE_MIPS16      = 0x266
    IMAGE_FILE_MACHINE_MIPSFPU     = 0x366
    IMAGE_FILE_MACHINE_MIPSFPU16   = 0x466
    IMAGE_FILE_MACHINE_POWERPC     = 0x1f0
    IMAGE_FILE_MACHINE_POWERPCFP   = 0x1f1
    IMAGE_FILE_MACHINE_R4000       = 0x166
    IMAGE_FILE_MACHINE_SH3         = 0x1a2
    IMAGE_FILE_MACHINE_SH3DSP      = 0x1a3
    IMAGE_FILE_MACHINE_SH4         = 0x1a6
    IMAGE_FILE_MACHINE_SH5         = 0x1a8
    IMAGE_FILE_MACHINE_THUMB       = 0x1c2
    IMAGE_FILE_MACHINE_WCEMIPSV2   = 0x169
    IMAGE_FILE_MACHINE_RISCV32     = 0x5032
    IMAGE_FILE_MACHINE_RISCV64     = 0x5064
    IMAGE_FILE_MACHINE_RISCV128    = 0x5128
)
```

IMAGE\_DIRECTORY\_ENTRY constants

```go
const (
    IMAGE_DIRECTORY_ENTRY_EXPORT         = 0
    IMAGE_DIRECTORY_ENTRY_IMPORT         = 1
    IMAGE_DIRECTORY_ENTRY_RESOURCE       = 2
    IMAGE_DIRECTORY_ENTRY_EXCEPTION      = 3
    IMAGE_DIRECTORY_ENTRY_SECURITY       = 4
    IMAGE_DIRECTORY_ENTRY_BASERELOC      = 5
    IMAGE_DIRECTORY_ENTRY_DEBUG          = 6
    IMAGE_DIRECTORY_ENTRY_ARCHITECTURE   = 7
    IMAGE_DIRECTORY_ENTRY_GLOBALPTR      = 8
    IMAGE_DIRECTORY_ENTRY_TLS            = 9
    IMAGE_DIRECTORY_ENTRY_LOAD_CONFIG    = 10
    IMAGE_DIRECTORY_ENTRY_BOUND_IMPORT   = 11
    _DIRECTORY_ENTRY_IAT            = 12
    IMAGE_DIRECTORY_ENTRY_DELAY_IMPORT   = 13
    IMAGE_DIRECTORY_ENTRY_COM_DESCRIPTOR = 14
)
```

Values of IMAGE\_FILE\_HEADER.Characteristics. These can be combined
together.

```go
const (
    IMAGE_FILE_RELOCS_STRIPPED         = 0x0001
    IMAGE_FILE_EXECUTABLE_IMAGE        = 0x0002
    IMAGE_FILE_LINE_NUMS_STRIPPED      = 0x0004
    IMAGE_FILE_LOCAL_SYMS_STRIPPED     = 0x0008
    IMAGE_FILE_AGGRESIVE_WS_TRIM       = 0x0010
    IMAGE_FILE_LARGE_ADDRESS_AWARE     = 0x0020
    IMAGE_FILE_BYTES_REVERSED_LO       = 0x0080
    IMAGE_FILE_32BIT_MACHINE           = 0x0100
    IMAGE_FILE_DEBUG_STRIPPED          = 0x0200
    IMAGE_FILE_REMOVABLE_RUN_FROM_SWAP = 0x0400
    IMAGE_FILE_NET_RUN_FROM_SWAP       = 0x0800
    IMAGE_FILE_SYSTEM                  = 0x1000
    IMAGE_FILE_DLL                     = 0x2000
    IMAGE_FILE_UP_SYSTEM_ONLY          = 0x4000
    IMAGE_FILE_BYTES_REVERSED_HI       = 0x8000
)
```

OptionalHeader64.Subsystem and OptionalHeader32.Subsystem values.

```go
const (
    IMAGE_SUBSYSTEM_UNKNOWN                  = 0
    IMAGE_SUBSYSTEM_NATIVE                   = 1
    IMAGE_SUBSYSTEM_WINDOWS_GUI              = 2
    IMAGE_SUBSYSTEM_WINDOWS_CUI              = 3
    IMAGE_SUBSYSTEM_OS2_CUI                  = 5
    IMAGE_SUBSYSTEM_POSIX_CUI                = 7
    IMAGE_SUBSYSTEM_NATIVE_WINDOWS           = 8
    IMAGE_SUBSYSTEM_WINDOWS_CE_GUI           = 9
    IMAGE_SUBSYSTEM_EFI_APPLICATION          = 10
    IMAGE_SUBSYSTEM_EFI_BOOT_SERVICE_DRIVER  = 11
    IMAGE_SUBSYSTEM_EFI_RUNTIME_DRIVER       = 12
    IMAGE_SUBSYSTEM_EFI_ROM                  = 13
    IMAGE_SUBSYSTEM_XBOX                     = 14
    IMAGE_SUBSYSTEM_WINDOWS_BOOT_APPLICATION = 16
)
```

OptionalHeader64.DllCharacteristics and
OptionalHeader32.DllCharacteristics values. These can be combined
together.

```go
const (
    IMAGE_DLLCHARACTERISTICS_HIGH_ENTROPY_VA       = 0x0020
    IMAGE_DLLCHARACTERISTICS_DYNAMIC_BASE          = 0x0040
    IMAGE_DLLCHARACTERISTICS_FORCE_INTEGRITY       = 0x0080
    IMAGE_DLLCHARACTERISTICS_NX_COMPAT             = 0x0100
    IMAGE_DLLCHARACTERISTICS_NO_ISOLATION          = 0x0200
    IMAGE_DLLCHARACTERISTICS_NO_SEH                = 0x0400
    IMAGE_DLLCHARACTERISTICS_NO_BIND               = 0x0800
    IMAGE_DLLCHARACTERISTICS_APPCONTAINER          = 0x1000
    IMAGE_DLLCHARACTERISTICS_WDM_DRIVER            = 0x2000
    IMAGE_DLLCHARACTERISTICS_GUARD_CF              = 0x4000
    IMAGE_DLLCHARACTERISTICS_TERMINAL_SERVER_AWARE = 0x8000
)
```

Section characteristics flags.

```go
const (
    IMAGE_SCN_CNT_CODE               = 0x00000020
    IMAGE_SCN_CNT_INITIALIZED_DATA   = 0x00000040
    IMAGE_SCN_CNT_UNINITIALIZED_DATA = 0x00000080
    IMAGE_SCN_LNK_COMDAT             = 0x00001000
    IMAGE_SCN_MEM_DISCARDABLE        = 0x02000000
    IMAGE_SCN_MEM_EXECUTE            = 0x20000000
    IMAGE_SCN_MEM_READ               = 0x40000000
    IMAGE_SCN_MEM_WRITE              = 0x80000000
)
```

These constants make up the possible values for the \'Selection\' field
in an AuxFormat5.

```go
const (
    IMAGE_COMDAT_SELECT_NODUPLICATES = 1
    IMAGE_COMDAT_SELECT_ANY          = 2
    IMAGE_COMDAT_SELECT_SAME_SIZE    = 3
    IMAGE_COMDAT_SELECT_EXACT_MATCH  = 4
    IMAGE_COMDAT_SELECT_ASSOCIATIVE  = 5
    IMAGE_COMDAT_SELECT_LARGEST      = 6
)
```

```go
const COFFSymbolSize = 18
```

type COFFSymbol 
----------------------------------------------

COFFSymbol represents single COFF symbol table record.

```go
type COFFSymbol struct {
    Name               [8]uint8
    Value              uint32
    SectionNumber      int16
    Type               uint16
    StorageClass       uint8
    NumberOfAuxSymbols uint8
}
```

### func (\*COFFSymbol) FullName 

```go
func (sym *COFFSymbol) FullName(st StringTable) (string, error)
```

FullName finds real name of symbol sym. Normally name is stored in
sym.Name, but if it is longer then 8 characters, it is stored in COFF
string table st instead.

type COFFSymbolAuxFormat5 
----------------------------------------------------------

COFFSymbolAuxFormat5 describes the expected form of an aux symbol
attached to a section definition symbol. The PE format defines a number
of different aux symbol formats: format 1 for function definitions,
format 2 for .be and .ef symbols, and so on. Format 5 holds extra info
associated with a section definition, including number of relocations +
line numbers, as well as COMDAT info. See
https://docs.microsoft.com/en-us/windows/win32/debug/pe-format#auxiliary-format-5-section-definitions>
for more on what\'s going on here.

```go
type COFFSymbolAuxFormat5 struct {
    Size           uint32
    NumRelocs      uint16
    NumLineNumbers uint16
    Checksum       uint32
    SecNum         uint16
    Selection      uint8
    // contains filtered or unexported fields
}
```

type DataDirectory 
-------------------------------------------------

```go
type DataDirectory struct {
    VirtualAddress uint32
    Size           uint32
}
```

type File 
---------

A File represents an open PE file.

```go
type File struct {
    FileHeader
    OptionalHeader any // of type *OptionalHeader32 or *OptionalHeader64; added in Go 1.3
    Sections       []*Section
    Symbols        []*Symbol    // COFF symbols with auxiliary symbol records removed; added in Go 1.1
    COFFSymbols    []COFFSymbol // all COFF symbols (including auxiliary symbol records); added in Go 1.8
    StringTable    StringTable // Go 1.8
    // contains filtered or unexported fields
}
```

### func NewFile 

```go
func NewFile(r io.ReaderAt) (*File, error)
```

NewFile creates a new File for accessing a PE binary in an underlying
reader.

### func Open 

```go
func Open(name string) (*File, error)
```

Open opens the named file using os.Open and prepares it for use as a PE
binary.

### func (\*File) COFFSymbolReadSectionDefAux 

```go
func (f *File) COFFSymbolReadSectionDefAux(idx int) (*COFFSymbolAuxFormat5, error)
```

COFFSymbolReadSectionDefAux returns a blob of auxiliary information
(including COMDAT info) for a section definition symbol. Here \'idx\' is
the index of a section symbol in the main COFFSymbol array for the File.
Return value is a pointer to the appropriate aux symbol struct. For more
info, see:

auxiliary symbols:
https://docs.microsoft.com/en-us/windows/win32/debug/pe-format#auxiliary-symbol-records>
COMDAT sections:
https://docs.microsoft.com/en-us/windows/win32/debug/pe-format#comdat-sections-object-only>
auxiliary info for section definitions:
https://docs.microsoft.com/en-us/windows/win32/debug/pe-format#auxiliary-format-5-section-definitions>

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

### func (\*File) ImportedLibraries 

```go
func (f *File) ImportedLibraries() ([]string, error)
```

ImportedLibraries returns the names of all libraries referred to by the
binary f that are expected to be linked with the binary at dynamic link
time.

### func (\*File) ImportedSymbols 

```go
func (f *File) ImportedSymbols() ([]string, error)
```

ImportedSymbols returns the names of all symbols referred to by the
binary f that are expected to be satisfied by other libraries at dynamic
load time. It does not return weak symbols.

### func (\*File) Section 

```go
func (f *File) Section(name string) *Section
```

Section returns the first section with the given name, or nil if no such
section exists.

type FileHeader 
---------------

```go
type FileHeader struct {
    Machine              uint16
    NumberOfSections     uint16
    TimeDateStamp        uint32
    PointerToSymbolTable uint32
    NumberOfSymbols      uint32
    SizeOfOptionalHeader uint16
    Characteristics      uint16
}
```

type FormatError 
----------------

FormatError is unused. The type is retained for compatibility.

```go
type FormatError struct {
}
```

### func (\*FormatError) Error 

```go
func (e *FormatError) Error() string
```

type ImportDirectory 
--------------------

```go
type ImportDirectory struct {
    OriginalFirstThunk uint32
    TimeDateStamp      uint32
    ForwarderChain     uint32
    Name               uint32
    FirstThunk         uint32
    // contains filtered or unexported fields
}
```

type OptionalHeader32 
----------------------------------------------------

```go
type OptionalHeader32 struct {
    Magic                       uint16
    MajorLinkerVersion          uint8
    MinorLinkerVersion          uint8
    SizeOfCode                  uint32
    SizeOfInitializedData       uint32
    SizeOfUninitializedData     uint32
    AddressOfEntryPoint         uint32
    BaseOfCode                  uint32
    BaseOfData                  uint32
    ImageBase                   uint32
    SectionAlignment            uint32
    FileAlignment               uint32
    MajorOperatingSystemVersion uint16
    MinorOperatingSystemVersion uint16
    MajorImageVersion           uint16
    MinorImageVersion           uint16
    MajorSubsystemVersion       uint16
    MinorSubsystemVersion       uint16
    Win32VersionValue           uint32
    SizeOfImage                 uint32
    SizeOfHeaders               uint32
    CheckSum                    uint32
    Subsystem                   uint16
    DllCharacteristics          uint16
    SizeOfStackReserve          uint32
    SizeOfStackCommit           uint32
    SizeOfHeapReserve           uint32
    SizeOfHeapCommit            uint32
    LoaderFlags                 uint32
    NumberOfRvaAndSizes         uint32
    DataDirectory               [16]DataDirectory
}
```

type OptionalHeader64 
----------------------------------------------------

```go
type OptionalHeader64 struct {
    Magic                       uint16
    MajorLinkerVersion          uint8
    MinorLinkerVersion          uint8
    SizeOfCode                  uint32
    SizeOfInitializedData       uint32
    SizeOfUninitializedData     uint32
    AddressOfEntryPoint         uint32
    BaseOfCode                  uint32
    ImageBase                   uint64
    SectionAlignment            uint32
    FileAlignment               uint32
    MajorOperatingSystemVersion uint16
    MinorOperatingSystemVersion uint16
    MajorImageVersion           uint16
    MinorImageVersion           uint16
    MajorSubsystemVersion       uint16
    MinorSubsystemVersion       uint16
    Win32VersionValue           uint32
    SizeOfImage                 uint32
    SizeOfHeaders               uint32
    CheckSum                    uint32
    Subsystem                   uint16
    DllCharacteristics          uint16
    SizeOfStackReserve          uint64
    SizeOfStackCommit           uint64
    SizeOfHeapReserve           uint64
    SizeOfHeapCommit            uint64
    LoaderFlags                 uint32
    NumberOfRvaAndSizes         uint32
    DataDirectory               [16]DataDirectory
}
```

type Reloc 
-----------------------------------------

Reloc represents a PE COFF relocation. Each section contains its own
relocation list.

```go
type Reloc struct {
    VirtualAddress   uint32
    SymbolTableIndex uint32
    Type             uint16
}
```

type Section 
------------

Section provides access to PE COFF section.

```go
type Section struct {
    SectionHeader
    Relocs []Reloc // Go 1.8

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

Data reads and returns the contents of the PE section s.

If s.Offset is 0, the section has no contents, and Data will always
return a non-nil error.

### func (\*Section) Open 

```go
func (s *Section) Open() io.ReadSeeker
```

Open returns a new ReadSeeker reading the PE section s.

If s.Offset is 0, the section has no contents, and all calls to the
returned reader will return a non-nil error.

type SectionHeader 
------------------

SectionHeader is similar to SectionHeader32 with Name field replaced by
Go string.

```go
type SectionHeader struct {
    Name                 string
    VirtualSize          uint32
    VirtualAddress       uint32
    Size                 uint32
    Offset               uint32
    PointerToRelocations uint32
    PointerToLineNumbers uint32
    NumberOfRelocations  uint16
    NumberOfLineNumbers  uint16
    Characteristics      uint32
}
```

type SectionHeader32 
--------------------

SectionHeader32 represents real PE COFF section header.

```go
type SectionHeader32 struct {
    Name                 [8]uint8
    VirtualSize          uint32
    VirtualAddress       uint32
    SizeOfRawData        uint32
    PointerToRawData     uint32
    PointerToRelocations uint32
    PointerToLineNumbers uint32
    NumberOfRelocations  uint16
    NumberOfLineNumbers  uint16
    Characteristics      uint32
}
```

type StringTable 
-----------------------------------------------

StringTable is a COFF string table.

```go
type StringTable []byte
```

### func (StringTable) String 

```go
func (st StringTable) String(start uint32) (string, error)
```

String extracts string from COFF string table st at offset start.

type Symbol 
------------------------------------------

Symbol is similar to COFFSymbol with Name field replaced by Go string.
Symbol also does not have NumberOfAuxSymbols.

```go
type Symbol struct {
    Name          string
    Value         uint32
    SectionNumber int16
    Type          uint16
    StorageClass  uint8
}
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/debug/pe/>

