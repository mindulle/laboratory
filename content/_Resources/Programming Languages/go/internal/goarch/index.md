Package goarch
==============

-   `import "internal/goarch"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

package goarch contains GOARCH-specific constants.

Index 
-----

-   [Constants](#pkg-constants)
-   [type ArchFamilyType](#ArchFamilyType)

### Package files

goarch.go goarch\_amd64.go zgoarch\_amd64.go

Constants 
---------

BigEndian reports whether the architecture is big-endian.

```go
const BigEndian = IsArmbe|IsArm64be|IsMips|IsMips64|IsPpc|IsPpc64|IsS390|IsS390x|IsSparc|IsSparc64 == 1
```

DefaultPhysPageSize is the default physical page size.

```go
const DefaultPhysPageSize = _DefaultPhysPageSize
```

```go
const GOARCH = `amd64`
```

Int64Align is the required alignment for a 64-bit integer (4 on 32-bit
systems, 8 on 64-bit).

```go
const Int64Align = PtrSize
```

```go
const Is386 = 0
```

```go
const IsAmd64 = 1
```

```go
const IsAmd64p32 = 0
```

```go
const IsArm = 0
```

```go
const IsArm64 = 0
```

```go
const IsArm64be = 0
```

```go
const IsArmbe = 0
```

```go
const IsLoong64 = 0
```

```go
const IsMips = 0
```

```go
const IsMips64 = 0
```

```go
const IsMips64le = 0
```

```go
const IsMips64p32 = 0
```

```go
const IsMips64p32le = 0
```

```go
const IsMipsle = 0
```

```go
const IsPpc = 0
```

```go
const IsPpc64 = 0
```

```go
const IsPpc64le = 0
```

```go
const IsRiscv = 0
```

```go
const IsRiscv64 = 0
```

```go
const IsS390 = 0
```

```go
const IsS390x = 0
```

```go
const IsSparc = 0
```

```go
const IsSparc64 = 0
```

```go
const IsWasm = 0
```

MinFrameSize is the size of the system-reserved words at the bottom of a
frame (just above the architectural stack pointer). It is zero on x86
and PtrSize on most non-x86 (LR-based) systems. On PowerPC it is larger,
to cover three more reserved words: the compiler word, the link editor
word, and the TOC save word.

```go
const MinFrameSize = _MinFrameSize
```

PCQuantum is the minimal unit for a program counter (1 on x86, 4 on most
other systems). The various PC tables record PC deltas pre-divided by
PCQuantum.

```go
const PCQuantum = _PCQuantum
```

PtrSize is the size of a pointer in bytes - unsafe.Sizeof(uintptr(0))
but as an ideal constant. It is also the size of the machine\'s native
word size (that is, 4 on 32-bit systems, 8 on 64-bit).

```go
const PtrSize = 4 << (^uintptr(0) >> 63)
```

StackAlign is the required alignment of the SP register. The stack must
be at least word aligned, but some architectures require more.

```go
const StackAlign = _StackAlign
```

type ArchFamilyType 
-------------------

```go
type ArchFamilyType int
```

```go
const (
    AMD64 ArchFamilyType = iota
    ARM
    ARM64
    I386
    LOONG64
    MIPS
    MIPS64
    PPC64
    RISCV64
    S390X
    WASM
)
```

ArchFamily is the architecture family (AMD64, ARM, \...)

```go
const ArchFamily ArchFamilyType = _ArchFamily
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/internal/goarch/>

