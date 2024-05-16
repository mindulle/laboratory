Package sha1
============

-   `import "crypto/sha1"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package sha1 implements the SHA-1 hash algorithm as defined in RFC 3174.

SHA-1 is cryptographically broken and should not be used for secure
applications.

Index 
-----

-   [Constants](#pkg-constants)
-   [func New() hash.Hash](#New)
-   [func Sum(data \[\]byte) \[Size\]byte](#Sum)

 
### Examples

[New](#example_New)

[New (File)](#example_New_file)

[Sum](#example_Sum)


### Package files

boring.go sha1.go sha1block.go sha1block\_amd64.go

Constants 
---------

The blocksize of SHA-1 in bytes.

```go
const BlockSize = 64
```

The size of a SHA-1 checksum in bytes.

```go
const Size = 20
```

func New 
--------

```go
func New() hash.Hash
```

New returns a new hash.Hash computing the SHA1 checksum. The Hash also
implements encoding.BinaryMarshaler and encoding.BinaryUnmarshaler to
marshal and unmarshal the internal state of the hash.

#### [Example]

Code:

```go
h := sha1.New()
io.WriteString(h, "His money is twice tainted:")
io.WriteString(h, " 'taint yours and 'taint mine.")
fmt.Printf("% x", h.Sum(nil))
```

Output:

```go
59 7f 6a 54 00 10 f9 4c 15 d7 18 06 a9 9a 2c 87 10 e7 47 bd
```

#### [Example (File)]

Code:

```go
f, err := os.Open("file.txt")
if err != nil {
    log.Fatal(err)
}
defer f.Close()

h := sha1.New()
if _, err := io.Copy(h, f); err != nil {
    log.Fatal(err)
}

fmt.Printf("% x", h.Sum(nil))
```

func Sum 
---------------------------------------

```go
func Sum(data []byte) [Size]byte
```

Sum returns the SHA-1 checksum of the data.

#### [Example]

Code:

```go
data := []byte("This page intentionally left blank.")
fmt.Printf("% x", sha1.Sum(data))
```

Output:

```go
af 06 49 23 bb f2 30 15 96 aa c4 c2 73 ba 32 17 8e bc 4a 96
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/crypto/sha1/>

