Package hash
============

-   `import "hash"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)
-   [Subdirectories](#pkg-subdirectories)

Overview 
--------

Package hash provides interfaces for hash functions.

#### [Example (BinaryMarshaler)]

Code:

```go
const (
    input1 = "The tunneling gopher digs downwards, "
    input2 = "unaware of what he will find."
)

first := sha256.New()
first.Write([]byte(input1))

marshaler, ok := first.(encoding.BinaryMarshaler)
if !ok {
    log.Fatal("first does not implement encoding.BinaryMarshaler")
}
state, err := marshaler.MarshalBinary()
if err != nil {
    log.Fatal("unable to marshal hash:", err)
}

second := sha256.New()

unmarshaler, ok := second.(encoding.BinaryUnmarshaler)
if !ok {
    log.Fatal("second does not implement encoding.BinaryUnmarshaler")
}
if err := unmarshaler.UnmarshalBinary(state); err != nil {
    log.Fatal("unable to unmarshal hash:", err)
}

first.Write([]byte(input2))
second.Write([]byte(input2))

fmt.Printf("%x\n", first.Sum(nil))
fmt.Println(bytes.Equal(first.Sum(nil), second.Sum(nil)))
```

Output:

```go
57d51a066f3a39942649cd9a76c77e97ceab246756ff3888659e6aa5a07f4a52
true
```

Index 
-----

-   [type Hash](#Hash)
-   [type Hash32](#Hash32)
-   [type Hash64](#Hash64)

 
### Examples

[Package (BinaryMarshaler)](#example__binaryMarshaler)


### Package files

hash.go

type Hash 
---------

Hash is the common interface implemented by all hash functions.

Hash implementations in the standard library (e.g. hash/crc32 and
crypto/sha256) implement the encoding.BinaryMarshaler and
encoding.BinaryUnmarshaler interfaces. Marshaling a hash implementation
allows its internal state to be saved and used for additional processing
later, without having to re-write the data previously written to the
hash. The hash state may contain portions of the input in its original
form, which users are expected to handle for any possible security
implications.

Compatibility: Any future changes to hash or crypto packages will
endeavor to maintain compatibility with state encoded using previous
versions. That is, any released versions of the packages should be able
to decode data written with any previously released version, subject to
issues such as security fixes. See the Go compatibility document for
background: https://golang.org/doc/go1compat>

```go
type Hash interface {
    // Write (via the embedded io.Writer interface) adds more data to the running hash.
    // It never returns an error.
    io.Writer

    // Sum appends the current hash to b and returns the resulting slice.
    // It does not change the underlying hash state.
    Sum(b []byte) []byte

    // Reset resets the Hash to its initial state.
    Reset()

    // Size returns the number of bytes Sum will return.
    Size() int

    // BlockSize returns the hash's underlying block size.
    // The Write method must be able to accept any amount
    // of data, but it may operate more efficiently if all writes
    // are a multiple of the block size.
    BlockSize() int
}
```

type Hash32 
-----------

Hash32 is the common interface implemented by all 32-bit hash functions.

```go
type Hash32 interface {
    Hash
    Sum32() uint32
}
```

type Hash64 
-----------

Hash64 is the common interface implemented by all 64-bit hash functions.

```go
type Hash64 interface {
    Hash
    Sum64() uint64
}
```

Subdirectories 
--------------

 
Name


Synopsis

[..](../index)

[adler32](adler32/index)

Package adler32 implements the Adler-32 checksum.

[crc32](crc32/index)

Package crc32 implements the 32-bit cyclic redundancy check, or CRC-32,
checksum.

[crc64](crc64/index)

Package crc64 implements the 64-bit cyclic redundancy check, or CRC-64,
checksum.

[fnv](fnv/index)

Package fnv implements FNV-1 and FNV-1a, non-cryptographic hash
functions created by Glenn Fowler, Landon Curt Noll, and Phong Vo.

[maphash](maphash/index)

Package maphash provides hash functions on byte sequences.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/hash/>

