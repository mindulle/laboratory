Package crc32
=============

-   `import "hash/crc32"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package crc32 implements the 32-bit cyclic redundancy check, or CRC-32,
checksum. See https://en.wikipedia.org/wiki/Cyclic_redundancy_check>
for information.

Polynomials are represented in LSB-first form also known as reversed
representation.

See
https://en.wikipedia.org/wiki/Mathematics_of_cyclic_redundancy_checks#Reversed_representations_and_reciprocal_polynomials>
for information.

Index 
-----

-   [Constants](#pkg-constants)
-   [Variables](#pkg-variables)
-   [func Checksum(data \[\]byte, tab \*Table) uint32](#Checksum)
-   [func ChecksumIEEE(data \[\]byte) uint32](#ChecksumIEEE)
-   [func New(tab \*Table) hash.Hash32](#New)
-   [func NewIEEE() hash.Hash32](#NewIEEE)
-   [func Update(crc uint32, tab \*Table, p \[\]byte) uint32](#Update)
-   [type Table](#Table)
-   [func MakeTable(poly uint32) \*Table](#MakeTable)

 
### Examples

[MakeTable](#example_MakeTable)


### Package files

crc32.go crc32\_amd64.go crc32\_generic.go

Constants 
---------

Predefined polynomials.

```go
const (
    // IEEE is by far and away the most common CRC-32 polynomial.
    // Used by ethernet (IEEE 802.3), v.42, fddi, gzip, zip, png, ...
    IEEE = 0xedb88320

    // Castagnoli's polynomial, used in iSCSI.
    // Has better error detection characteristics than IEEE.
    // https://dx.doi.org/10.1109/26.231911
    Castagnoli = 0x82f63b78

    // Koopman's polynomial.
    // Also has better error detection characteristics than IEEE.
    // https://dx.doi.org/10.1109/DSN.2002.1028931
    Koopman = 0xeb31d82e
)
```

The size of a CRC-32 checksum in bytes.

```go
const Size = 4
```

Variables 
---------

IEEETable is the table for the IEEE polynomial.

```go
var IEEETable = simpleMakeTable(IEEE)
```

func Checksum 
-------------

```go
func Checksum(data []byte, tab *Table) uint32
```

Checksum returns the CRC-32 checksum of data using the polynomial
represented by the Table.

func ChecksumIEEE 
-----------------

```go
func ChecksumIEEE(data []byte) uint32
```

ChecksumIEEE returns the CRC-32 checksum of data using the IEEE
polynomial.

func New 
--------

```go
func New(tab *Table) hash.Hash32
```

New creates a new hash.Hash32 computing the CRC-32 checksum using the
polynomial represented by the Table. Its Sum method will lay the value
out in big-endian byte order. The returned Hash32 also implements
encoding.BinaryMarshaler and encoding.BinaryUnmarshaler to marshal and
unmarshal the internal state of the hash.

func NewIEEE 
------------

```go
func NewIEEE() hash.Hash32
```

NewIEEE creates a new hash.Hash32 computing the CRC-32 checksum using
the IEEE polynomial. Its Sum method will lay the value out in big-endian
byte order. The returned Hash32 also implements encoding.BinaryMarshaler
and encoding.BinaryUnmarshaler to marshal and unmarshal the internal
state of the hash.

func Update 
-----------

```go
func Update(crc uint32, tab *Table, p []byte) uint32
```

Update returns the result of adding the bytes in p to the crc.

type Table 
----------

Table is a 256-word table representing the polynomial for efficient
processing.

```go
type Table [256]uint32
```

### func MakeTable 

```go
func MakeTable(poly uint32) *Table
```

MakeTable returns a Table constructed from the specified polynomial. The
contents of this Table must not be modified.

#### [Example]

Code:

```go
// In this package, the CRC polynomial is represented in reversed notation,
// or LSB-first representation.
//
// LSB-first representation is a hexadecimal number with n bits, in which the
// most significant bit represents the coefficient of x⁰ and the least significant
// bit represents the coefficient of xⁿ⁻¹ (the coefficient for xⁿ is implicit).
//
// For example, CRC32-Q, as defined by the following polynomial,
//  x³²+ x³¹+ x²⁴+ x²²+ x¹⁶+ x¹⁴+ x⁸+ x⁷+ x⁵+ x³+ x¹+ x⁰
// has the reversed notation 0b11010101100000101000001010000001, so the value
// that should be passed to MakeTable is 0xD5828281.
crc32q := crc32.MakeTable(0xD5828281)
fmt.Printf("%08x\n", crc32.Checksum([]byte("Hello world"), crc32q))
```

Output:

```go
2964d064
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/hash/crc32/>

