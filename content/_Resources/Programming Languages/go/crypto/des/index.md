Package des
===========

-   `import "crypto/des"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package des implements the Data Encryption Standard (DES) and the Triple
Data Encryption Algorithm (TDEA) as defined in U.S. Federal Information
Processing Standards Publication 46-3.

DES is cryptographically broken and should not be used for secure
applications.

Index 
-----

-   [Constants](#pkg-constants)
-   [func NewCipher(key \[\]byte) (cipher.Block, error)](#NewCipher)
-   [func NewTripleDESCipher(key \[\]byte) (cipher.Block,
    error)](#NewTripleDESCipher)
-   [type KeySizeError](#KeySizeError)
-   [func (k KeySizeError) Error() string](#KeySizeError.Error)

 
### Examples

[NewTripleDESCipher](#example_NewTripleDESCipher)


### Package files

block.go cipher.go const.go

Constants 
---------

The DES block size in bytes.

```go
const BlockSize = 8
```

func NewCipher 
--------------

```go
func NewCipher(key []byte) (cipher.Block, error)
```

NewCipher creates and returns a new cipher.Block.

func NewTripleDESCipher 
-----------------------

```go
func NewTripleDESCipher(key []byte) (cipher.Block, error)
```

NewTripleDESCipher creates and returns a new cipher.Block.

#### [Example]

Code:

```go
// NewTripleDESCipher can also be used when EDE2 is required by
// duplicating the first 8 bytes of the 16-byte key.
ede2Key := []byte("example key 1234")

var tripleDESKey []byte
tripleDESKey = append(tripleDESKey, ede2Key[:16]...)
tripleDESKey = append(tripleDESKey, ede2Key[:8]...)

_, err := des.NewTripleDESCipher(tripleDESKey)
if err != nil {
    panic(err)
}

// See crypto/cipher for how to use a cipher.Block for encryption and
// decryption.
```

type KeySizeError 
-----------------

```go
type KeySizeError int
```

### func (KeySizeError) Error 

```go
func (k KeySizeError) Error() string
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/crypto/des/>

