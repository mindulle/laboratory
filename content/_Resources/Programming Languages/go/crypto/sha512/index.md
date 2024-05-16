Package sha512
==============

-   `import "crypto/sha512"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package sha512 implements the SHA-384, SHA-512, SHA-512/224, and
SHA-512/256 hash algorithms as defined in FIPS 180-4.

All the hash.Hash implementations returned by this package also
implement encoding.BinaryMarshaler and encoding.BinaryUnmarshaler to
marshal and unmarshal the internal state of the hash.

Index 
-----

-   [Constants](#pkg-constants)
-   [func New() hash.Hash](#New)
-   [func New384() hash.Hash](#New384)
-   [func New512\_224() hash.Hash](#New512_224)
-   [func New512\_256() hash.Hash](#New512_256)
-   [func Sum384(data \[\]byte) \[Size384\]byte](#Sum384)
-   [func Sum512(data \[\]byte) \[Size\]byte](#Sum512)
-   [func Sum512\_224(data \[\]byte) \[Size224\]byte](#Sum512_224)
-   [func Sum512\_256(data \[\]byte) \[Size256\]byte](#Sum512_256)

### Package files

sha512.go sha512block.go sha512block\_amd64.go

Constants 
---------

```go
const (
    // Size is the size, in bytes, of a SHA-512 checksum.
    Size = 64

    // Size224 is the size, in bytes, of a SHA-512/224 checksum.
    Size224 = 28

    // Size256 is the size, in bytes, of a SHA-512/256 checksum.
    Size256 = 32

    // Size384 is the size, in bytes, of a SHA-384 checksum.
    Size384 = 48

    // BlockSize is the block size, in bytes, of the SHA-512/224,
    // SHA-512/256, SHA-384 and SHA-512 hash functions.
    BlockSize = 128
)
```

func New 
--------

```go
func New() hash.Hash
```

New returns a new hash.Hash computing the SHA-512 checksum.

func New384 
-----------

```go
func New384() hash.Hash
```

New384 returns a new hash.Hash computing the SHA-384 checksum.

func New512\_224 
-----------------------------------------------

```go
func New512_224() hash.Hash
```

New512\_224 returns a new hash.Hash computing the SHA-512/224 checksum.

func New512\_256 
-----------------------------------------------

```go
func New512_256() hash.Hash
```

New512\_256 returns a new hash.Hash computing the SHA-512/256 checksum.

func Sum384 
------------------------------------------

```go
func Sum384(data []byte) [Size384]byte
```

Sum384 returns the SHA384 checksum of the data.

func Sum512 
------------------------------------------

```go
func Sum512(data []byte) [Size]byte
```

Sum512 returns the SHA512 checksum of the data.

func Sum512\_224 
-----------------------------------------------

```go
func Sum512_224(data []byte) [Size224]byte
```

Sum512\_224 returns the Sum512/224 checksum of the data.

func Sum512\_256 
-----------------------------------------------

```go
func Sum512_256(data []byte) [Size256]byte
```

Sum512\_256 returns the Sum512/256 checksum of the data.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/crypto/sha512/>

