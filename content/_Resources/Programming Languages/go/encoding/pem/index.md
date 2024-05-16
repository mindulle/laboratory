Package pem
===========

-   `import "encoding/pem"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package pem implements the PEM data encoding, which originated in
Privacy Enhanced Mail. The most common use of PEM encoding today is in
TLS keys and certificates. See RFC 1421.

Index 
-----

-   [func Encode(out io.Writer, b \*Block) error](#Encode)
-   [func EncodeToMemory(b \*Block) \[\]byte](#EncodeToMemory)
-   [type Block](#Block)
-   [func Decode(data \[\]byte) (p \*Block, rest \[\]byte)](#Decode)

 
### Examples

[Decode](#example_Decode)

[Encode](#example_Encode)


### Package files

pem.go

func Encode 
-----------

```go
func Encode(out io.Writer, b *Block) error
```

Encode writes the PEM encoding of b to out.

#### [Example]

Code:

```go
block := &pem.Block{
    Type: "MESSAGE",
    Headers: map[string]string{
        "Animal": "Gopher",
    },
    Bytes: []byte("test"),
}

if err := pem.Encode(os.Stdout, block); err != nil {
    log.Fatal(err)
}
```

Output:

```go
-----BEGIN MESSAGE-----
Animal: Gopher

dGVzdA==
-----END MESSAGE-----
```

func EncodeToMemory 
-------------------

```go
func EncodeToMemory(b *Block) []byte
```

EncodeToMemory returns the PEM encoding of b.

If b has invalid headers and cannot be encoded, EncodeToMemory returns
nil. If it is important to report details about this error case, use
Encode instead.

type Block 
----------

A Block represents a PEM encoded structure.

The encoded form is:

```go
-----BEGIN Type-----
Headers
base64-encoded Bytes
-----END Type-----
```

where Headers is a possibly empty sequence of Key: Value lines.

```go
type Block struct {
    Type    string            // The type, taken from the preamble (i.e. "RSA PRIVATE KEY").
    Headers map[string]string // Optional headers.
    Bytes   []byte            // The decoded bytes of the contents. Typically a DER encoded ASN.1 structure.
}
```

### func Decode 

```go
func Decode(data []byte) (p *Block, rest []byte)
```

Decode will find the next PEM formatted block (certificate, private key
etc) in the input. It returns that block and the remainder of the input.
If no PEM data is found, p is nil and the whole of the input is returned
in rest.

#### [Example]

Code:

```go
var pubPEMData = []byte(`
-----BEGIN PUBLIC KEY-----
MIICIjANBgkqhkiG9w0BAQEFAAOCAg8AMIICCgKCAgEAlRuRnThUjU8/prwYxbty
WPT9pURI3lbsKMiB6Fn/VHOKE13p4D8xgOCADpdRagdT6n4etr9atzDKUSvpMtR3
CP5noNc97WiNCggBjVWhs7szEe8ugyqF23XwpHQ6uV1LKH50m92MbOWfCtjU9p/x
qhNpQQ1AZhqNy5Gevap5k8XzRmjSldNAFZMY7Yv3Gi+nyCwGwpVtBUwhuLzgNFK/
yDtw2WcWmUU7NuC8Q6MWvPebxVtCfVp/iQU6q60yyt6aGOBkhAX0LpKAEhKidixY
nP9PNVBvxgu3XZ4P36gZV6+ummKdBVnc3NqwBLu5+CcdRdusmHPHd5pHf4/38Z3/
6qU2a/fPvWzceVTEgZ47QjFMTCTmCwNt29cvi7zZeQzjtwQgn4ipN9NibRH/Ax/q
TbIzHfrJ1xa2RteWSdFjwtxi9C20HUkjXSeI4YlzQMH0fPX6KCE7aVePTOnB69I/
a9/q96DiXZajwlpq3wFctrs1oXqBp5DVrCIj8hU2wNgB7LtQ1mCtsYz//heai0K9
PhE4X6hiE0YmeAZjR0uHl8M/5aW9xCoJ72+12kKpWAa0SFRWLy6FejNYCYpkupVJ
yecLk/4L1W0l6jQQZnWErXZYe0PNFcmwGXy1Rep83kfBRNKRy5tvocalLlwXLdUk
AIU+2GKjyT3iMuzZxxFxPFMCAwEAAQ==
-----END PUBLIC KEY-----
and some more`)

block, rest := pem.Decode(pubPEMData)
if block == nil || block.Type != "PUBLIC KEY" {
    log.Fatal("failed to decode PEM block containing public key")
}

pub, err := x509.ParsePKIXPublicKey(block.Bytes)
if err != nil {
    log.Fatal(err)
}

fmt.Printf("Got a %T, with remaining data: %q", pub, rest)
```

Output:

```go
Got a *rsa.PublicKey, with remaining data: "and some more"
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/encoding/pem/>

