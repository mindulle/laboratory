Package ed25519
===============

-   `import "crypto/ed25519"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package ed25519 implements the Ed25519 signature algorithm. See
https://ed25519.cr.yp.to/>.

These functions are also compatible with the "Ed25519" function defined
in RFC 8032. However, unlike RFC 8032\'s formulation, this package\'s
private key representation includes a public key suffix to make multiple
signing operations with the same key more efficient. This package refers
to the RFC 8032 private key as the "seed".

#### [Example (Ed25519ctx)]

Code:

```go
pub, priv, err := GenerateKey(nil)
if err != nil {
    log.Fatal(err)
}

msg := []byte("The quick brown fox jumps over the lazy dog")

sig, err := priv.Sign(nil, msg, &Options{
    Context: "Example_ed25519ctx",
})
if err != nil {
    log.Fatal(err)
}

if err := VerifyWithOptions(pub, msg, sig, &Options{
    Context: "Example_ed25519ctx",
}); err != nil {
    log.Fatal("invalid signature")
}
```

Index 
-----

-   [Constants](#pkg-constants)
-   [func GenerateKey(rand io.Reader) (PublicKey, PrivateKey,
    error)](#GenerateKey)
-   [func Sign(privateKey PrivateKey, message \[\]byte) \[\]byte](#Sign)
-   [func Verify(publicKey PublicKey, message, sig \[\]byte)
    bool](#Verify)
-   [func VerifyWithOptions(publicKey PublicKey, message, sig \[\]byte,
    opts \*Options) error](#VerifyWithOptions)
-   [type Options](#Options)
-   [func (o \*Options) HashFunc() crypto.Hash](#Options.HashFunc)
-   [type PrivateKey](#PrivateKey)
-   [func NewKeyFromSeed(seed \[\]byte) PrivateKey](#NewKeyFromSeed)
-   [func (priv PrivateKey) Equal(x crypto.PrivateKey)
    bool](#PrivateKey.Equal)
-   [func (priv PrivateKey) Public()
    crypto.PublicKey](#PrivateKey.Public)
-   [func (priv PrivateKey) Seed() \[\]byte](#PrivateKey.Seed)
-   [func (priv PrivateKey) Sign(rand io.Reader, message \[\]byte, opts
    crypto.SignerOpts) (signature \[\]byte, err
    error)](#PrivateKey.Sign)
-   [type PublicKey](#PublicKey)
-   [func (pub PublicKey) Equal(x crypto.PublicKey)
    bool](#PublicKey.Equal)

 
### Examples

[Package (Ed25519ctx)](#example__ed25519ctx)


### Package files

ed25519.go

Constants 
---------

```go
const (
    // PublicKeySize is the size, in bytes, of public keys as used in this package.
    PublicKeySize = 32
    // PrivateKeySize is the size, in bytes, of private keys as used in this package.
    PrivateKeySize = 64
    // SignatureSize is the size, in bytes, of signatures generated and verified by this package.
    SignatureSize = 64
    // SeedSize is the size, in bytes, of private key seeds. These are the private key representations used by RFC 8032.
    SeedSize = 32
)
```

func GenerateKey 
-------------------------------------------------

```go
func GenerateKey(rand io.Reader) (PublicKey, PrivateKey, error)
```

GenerateKey generates a public/private key pair using entropy from rand.
If rand is nil, crypto/rand.Reader will be used.

The output of this function is deterministic, and equivalent to reading
[SeedSize](#SeedSize) bytes from rand, and passing them to
[NewKeyFromSeed](#NewKeyFromSeed).

func Sign 
------------------------------------------

```go
func Sign(privateKey PrivateKey, message []byte) []byte
```

Sign signs the message with privateKey and returns a signature. It will
panic if len(privateKey) is not [PrivateKeySize](#PrivateKeySize).

func Verify 
--------------------------------------------

```go
func Verify(publicKey PublicKey, message, sig []byte) bool
```

Verify reports whether sig is a valid signature of message by publicKey.
It will panic if len(publicKey) is not [PublicKeySize](#PublicKeySize).

func VerifyWithOptions 
-------------------------------------------------------

```go
func VerifyWithOptions(publicKey PublicKey, message, sig []byte, opts *Options) error
```

VerifyWithOptions reports whether sig is a valid signature of message by
publicKey. A valid signature is indicated by returning a nil error. It
will panic if len(publicKey) is not [PublicKeySize](#PublicKeySize).

If opts.Hash is crypto.SHA512, the pre-hashed variant Ed25519ph is used
and message is expected to be a SHA-512 hash, otherwise opts.Hash must
be crypto.Hash(0) and the message must not be hashed, as Ed25519
performs two passes over messages to be signed.

type Options 
---------------------------------------------

Options can be used with [PrivateKey.Sign](#PrivateKey.Sign) or
[VerifyWithOptions](#VerifyWithOptions) to select Ed25519 variants.

```go
type Options struct {
    // Hash can be zero for regular Ed25519, or crypto.SHA512 for Ed25519ph.
    Hash crypto.Hash

    // Context, if not empty, selects Ed25519ctx or provides the context string
    // for Ed25519ph. It can be at most 255 bytes in length.
    Context string
}
```

### func (\*Options) HashFunc 

```go
func (o *Options) HashFunc() crypto.Hash
```

HashFunc returns o.Hash.

type PrivateKey 
------------------------------------------------

PrivateKey is the type of Ed25519 private keys. It implements
crypto.Signer.

```go
type PrivateKey []byte
```

### func NewKeyFromSeed 

```go
func NewKeyFromSeed(seed []byte) PrivateKey
```

NewKeyFromSeed calculates a private key from a seed. It will panic if
len(seed) is not [SeedSize](#SeedSize). This function is provided for
interoperability with RFC 8032. RFC 8032\'s private keys correspond to
seeds in this package.

### func (PrivateKey) Equal 

```go
func (priv PrivateKey) Equal(x crypto.PrivateKey) bool
```

Equal reports whether priv and x have the same value.

### func (PrivateKey) Public 

```go
func (priv PrivateKey) Public() crypto.PublicKey
```

Public returns the [PublicKey](#PublicKey) corresponding to priv.

### func (PrivateKey) Seed 

```go
func (priv PrivateKey) Seed() []byte
```

Seed returns the private key seed corresponding to priv. It is provided
for interoperability with RFC 8032. RFC 8032\'s private keys correspond
to seeds in this package.

### func (PrivateKey) Sign 

```go
func (priv PrivateKey) Sign(rand io.Reader, message []byte, opts crypto.SignerOpts) (signature []byte, err error)
```

Sign signs the given message with priv. rand is ignored and can be nil.

If opts.HashFunc() is crypto.SHA512, the pre-hashed variant Ed25519ph is
used and message is expected to be a SHA-512 hash, otherwise
opts.HashFunc() must be crypto.Hash(0) and the message must not be
hashed, as Ed25519 performs two passes over messages to be signed.

A value of type [Options](#Options) can be used as opts, or
crypto.Hash(0) or crypto.SHA512 directly to select plain Ed25519 or
Ed25519ph, respectively.

type PublicKey 
-----------------------------------------------

PublicKey is the type of Ed25519 public keys.

```go
type PublicKey []byte
```

### func (PublicKey) Equal 

```go
func (pub PublicKey) Equal(x crypto.PublicKey) bool
```

Equal reports whether pub and x have the same value.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/crypto/ed25519/>

