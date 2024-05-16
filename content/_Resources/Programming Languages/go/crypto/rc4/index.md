Package rc4
===========

-   `import "crypto/rc4"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package rc4 implements RC4 encryption, as defined in Bruce Schneier\'s
Applied Cryptography.

RC4 is cryptographically broken and should not be used for secure
applications.

Index 
-----

-   [type Cipher](#Cipher)
-   [func NewCipher(key \[\]byte) (\*Cipher, error)](#NewCipher)
-   [func (c \*Cipher) Reset()](#Cipher.Reset)
-   [func (c \*Cipher) XORKeyStream(dst, src
    \[\]byte)](#Cipher.XORKeyStream)
-   [type KeySizeError](#KeySizeError)
-   [func (k KeySizeError) Error() string](#KeySizeError.Error)

### Package files

rc4.go

type Cipher 
-----------

A Cipher is an instance of RC4 using a particular key.

```go
type Cipher struct {
    // contains filtered or unexported fields
}
```

### func NewCipher 

```go
func NewCipher(key []byte) (*Cipher, error)
```

NewCipher creates and returns a new Cipher. The key argument should be
the RC4 key, at least 1 byte and at most 256 bytes.

### func (\*Cipher) Reset 

```go
func (c *Cipher) Reset()
```

Reset zeros the key data and makes the Cipher unusable.

Deprecated: Reset can\'t guarantee that the key will be entirely removed
from the process\'s memory.

### func (\*Cipher) XORKeyStream 

```go
func (c *Cipher) XORKeyStream(dst, src []byte)
```

XORKeyStream sets dst to the result of XORing src with the key stream.
Dst and src must overlap entirely or not at all.

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
https://golang.org/pkg/crypto/rc4/>

