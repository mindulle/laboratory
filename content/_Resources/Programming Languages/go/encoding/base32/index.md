Package base32
==============

-   `import "encoding/base32"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package base32 implements base32 encoding as specified by RFC 4648.

Index 
-----

-   [Constants](#pkg-constants)
-   [Variables](#pkg-variables)
-   [func NewDecoder(enc \*Encoding, r io.Reader)
    io.Reader](#NewDecoder)
-   [func NewEncoder(enc \*Encoding, w io.Writer)
    io.WriteCloser](#NewEncoder)
-   [type CorruptInputError](#CorruptInputError)
-   [func (e CorruptInputError) Error()
    string](#CorruptInputError.Error)
-   [type Encoding](#Encoding)
-   [func NewEncoding(encoder string) \*Encoding](#NewEncoding)
-   [func (enc \*Encoding) Decode(dst, src \[\]byte) (n int, err
    error)](#Encoding.Decode)
-   [func (enc \*Encoding) DecodeString(s string) (\[\]byte,
    error)](#Encoding.DecodeString)
-   [func (enc \*Encoding) DecodedLen(n int) int](#Encoding.DecodedLen)
-   [func (enc \*Encoding) Encode(dst, src \[\]byte)](#Encoding.Encode)
-   [func (enc \*Encoding) EncodeToString(src \[\]byte)
    string](#Encoding.EncodeToString)
-   [func (enc \*Encoding) EncodedLen(n int) int](#Encoding.EncodedLen)
-   [func (enc Encoding) WithPadding(padding rune)
    \*Encoding](#Encoding.WithPadding)

 
### Examples

[Encoding.Decode](#example_Encoding_Decode)

[Encoding.DecodeString](#example_Encoding_DecodeString)

[Encoding.Encode](#example_Encoding_Encode)

[Encoding.EncodeToString](#example_Encoding_EncodeToString)

[NewEncoder](#example_NewEncoder)


### Package files

base32.go

Constants 
---------

```go
const (
    StdPadding rune = '=' // Standard padding character
    NoPadding  rune = -1  // No padding

)
```

Variables 
---------

HexEncoding is the "Extended Hex Alphabet" defined in RFC 4648. It is
typically used in DNS.

```go
var HexEncoding = NewEncoding(encodeHex)
```

StdEncoding is the standard base32 encoding, as defined in RFC 4648.

```go
var StdEncoding = NewEncoding(encodeStd)
```

func NewDecoder 
---------------

```go
func NewDecoder(enc *Encoding, r io.Reader) io.Reader
```

NewDecoder constructs a new base32 stream decoder.

func NewEncoder 
---------------

```go
func NewEncoder(enc *Encoding, w io.Writer) io.WriteCloser
```

NewEncoder returns a new base32 stream encoder. Data written to the
returned writer will be encoded using enc and then written to w. Base32
encodings operate in 5-byte blocks; when finished writing, the caller
must Close the returned encoder to flush any partially written blocks.

#### [Example]

Code:

```go
input := []byte("foo\x00bar")
encoder := base32.NewEncoder(base32.StdEncoding, os.Stdout)
encoder.Write(input)
// Must close the encoder when finished to flush any partial blocks.
// If you comment out the following line, the last partial block "r"
// won't be encoded.
encoder.Close()
```

Output:

```go
MZXW6ADCMFZA====
```

type CorruptInputError 
----------------------

```go
type CorruptInputError int64
```

### func (CorruptInputError) Error 

```go
func (e CorruptInputError) Error() string
```

type Encoding 
-------------

An Encoding is a radix 32 encoding/decoding scheme, defined by a
32-character alphabet. The most common is the \"base32\" encoding
introduced for SASL GSSAPI and standardized in RFC 4648. The alternate
\"base32hex\" encoding is used in DNSSEC.

```go
type Encoding struct {
    // contains filtered or unexported fields
}
```

### func NewEncoding 

```go
func NewEncoding(encoder string) *Encoding
```

NewEncoding returns a new Encoding defined by the given alphabet, which
must be a 32-byte string. The alphabet is treated as sequence of byte
values without any special treatment for multi-byte UTF-8.

### func (\*Encoding) Decode 

```go
func (enc *Encoding) Decode(dst, src []byte) (n int, err error)
```

Decode decodes src using the encoding enc. It writes at most
DecodedLen(len(src)) bytes to dst and returns the number of bytes
written. If src contains invalid base32 data, it will return the number
of bytes successfully written and CorruptInputError. New line characters
(\\r and \\n) are ignored.

#### [Example]

Code:

```go
str := "JBSWY3DPFQQHO33SNRSCC==="
dst := make([]byte, base32.StdEncoding.DecodedLen(len(str)))
n, err := base32.StdEncoding.Decode(dst, []byte(str))
if err != nil {
    fmt.Println("decode error:", err)
    return
}
dst = dst[:n]
fmt.Printf("%q\n", dst)
```

Output:

```go
"Hello, world!"
```

### func (\*Encoding) DecodeString 

```go
func (enc *Encoding) DecodeString(s string) ([]byte, error)
```

DecodeString returns the bytes represented by the base32 string s.

#### [Example]

Code:

```go
str := "ONXW2ZJAMRQXIYJAO5UXI2BAAAQGC3TEEDX3XPY="
data, err := base32.StdEncoding.DecodeString(str)
if err != nil {
    fmt.Println("error:", err)
    return
}
fmt.Printf("%q\n", data)
```

Output:

```go
"some data with \x00 and \ufeff"
```

### func (\*Encoding) DecodedLen 

```go
func (enc *Encoding) DecodedLen(n int) int
```

DecodedLen returns the maximum length in bytes of the decoded data
corresponding to n bytes of base32-encoded data.

### func (\*Encoding) Encode 

```go
func (enc *Encoding) Encode(dst, src []byte)
```

Encode encodes src using the encoding enc, writing EncodedLen(len(src))
bytes to dst.

The encoding pads the output to a multiple of 8 bytes, so Encode is not
appropriate for use on individual blocks of a large data stream. Use
NewEncoder() instead.

#### [Example]

Code:

```go
data := []byte("Hello, world!")
dst := make([]byte, base32.StdEncoding.EncodedLen(len(data)))
base32.StdEncoding.Encode(dst, data)
fmt.Println(string(dst))
```

Output:

```go
JBSWY3DPFQQHO33SNRSCC===
```

### func (\*Encoding) EncodeToString 

```go
func (enc *Encoding) EncodeToString(src []byte) string
```

EncodeToString returns the base32 encoding of src.

#### [Example]

Code:

```go
data := []byte("any + old & data")
str := base32.StdEncoding.EncodeToString(data)
fmt.Println(str)
```

Output:

```go
MFXHSIBLEBXWYZBAEYQGIYLUME======
```

### func (\*Encoding) EncodedLen 

```go
func (enc *Encoding) EncodedLen(n int) int
```

EncodedLen returns the length in bytes of the base32 encoding of an
input buffer of length n.

### func (Encoding) WithPadding 

```go
func (enc Encoding) WithPadding(padding rune) *Encoding
```

WithPadding creates a new encoding identical to enc except with a
specified padding character, or NoPadding to disable padding. The
padding character must not be \'\\r\' or \'\\n\', must not be contained
in the encoding\'s alphabet and must be a rune equal or below \'\\xff\'.
Padding characters above \'\\x7f\' are encoded as their exact byte value
rather than using the UTF-8 representation of the codepoint.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/encoding/base32/>

