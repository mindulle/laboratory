Package hex
===========

-   `import "encoding/hex"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package hex implements hexadecimal encoding and decoding.

Index 
-----

-   [Variables](#pkg-variables)
-   [func Decode(dst, src \[\]byte) (int, error)](#Decode)
-   [func DecodeString(s string) (\[\]byte, error)](#DecodeString)
-   [func DecodedLen(x int) int](#DecodedLen)
-   [func Dump(data \[\]byte) string](#Dump)
-   [func Dumper(w io.Writer) io.WriteCloser](#Dumper)
-   [func Encode(dst, src \[\]byte) int](#Encode)
-   [func EncodeToString(src \[\]byte) string](#EncodeToString)
-   [func EncodedLen(n int) int](#EncodedLen)
-   [func NewDecoder(r io.Reader) io.Reader](#NewDecoder)
-   [func NewEncoder(w io.Writer) io.Writer](#NewEncoder)
-   [type InvalidByteError](#InvalidByteError)
-   [func (e InvalidByteError) Error() string](#InvalidByteError.Error)

 
### Examples

[Decode](#example_Decode)

[DecodeString](#example_DecodeString)

[Dump](#example_Dump)

[Dumper](#example_Dumper)

[Encode](#example_Encode)

[EncodeToString](#example_EncodeToString)


### Package files

hex.go

Variables 
---------

ErrLength reports an attempt to decode an odd-length input using Decode
or DecodeString. The stream-based Decoder returns io.ErrUnexpectedEOF
instead of ErrLength.

```go
var ErrLength = errors.New("encoding/hex: odd length hex string")
```

func Decode 
-----------

```go
func Decode(dst, src []byte) (int, error)
```

Decode decodes src into DecodedLen(len(src)) bytes, returning the actual
number of bytes written to dst.

Decode expects that src contains only hexadecimal characters and that
src has even length. If the input is malformed, Decode returns the
number of bytes decoded before the error.

#### [Example]

Code:

```go
src := []byte("48656c6c6f20476f7068657221")

dst := make([]byte, hex.DecodedLen(len(src)))
n, err := hex.Decode(dst, src)
if err != nil {
    log.Fatal(err)
}

fmt.Printf("%s\n", dst[:n])
```

Output:

```go
Hello Gopher!
```

func DecodeString 
-----------------

```go
func DecodeString(s string) ([]byte, error)
```

DecodeString returns the bytes represented by the hexadecimal string s.

DecodeString expects that src contains only hexadecimal characters and
that src has even length. If the input is malformed, DecodeString
returns the bytes decoded before the error.

#### [Example]

Code:

```go
const s = "48656c6c6f20476f7068657221"
decoded, err := hex.DecodeString(s)
if err != nil {
    log.Fatal(err)
}

fmt.Printf("%s\n", decoded)
```

Output:

```go
Hello Gopher!
```

func DecodedLen 
---------------

```go
func DecodedLen(x int) int
```

DecodedLen returns the length of a decoding of x source bytes.
Specifically, it returns x / 2.

func Dump 
---------

```go
func Dump(data []byte) string
```

Dump returns a string that contains a hex dump of the given data. The
format of the hex dump matches the output of \`hexdump -C\` on the
command line.

#### [Example]

Code:

```go
content := []byte("Go is an open source programming language.")

fmt.Printf("%s", hex.Dump(content))
```

Output:

```go
00000000  47 6f 20 69 73 20 61 6e  20 6f 70 65 6e 20 73 6f  |Go is an open so|
00000010  75 72 63 65 20 70 72 6f  67 72 61 6d 6d 69 6e 67  |urce programming|
00000020  20 6c 61 6e 67 75 61 67  65 2e                    | language.|
```

func Dumper 
-----------

```go
func Dumper(w io.Writer) io.WriteCloser
```

Dumper returns a WriteCloser that writes a hex dump of all written data
to w. The format of the dump matches the output of \`hexdump -C\` on the
command line.

#### [Example]

Code:

```go
lines := []string{
    "Go is an open source programming language.",
    "\n",
    "We encourage all Go users to subscribe to golang-announce.",
}

stdoutDumper := hex.Dumper(os.Stdout)

defer stdoutDumper.Close()

for _, line := range lines {
    stdoutDumper.Write([]byte(line))
}
```

Output:

```go
00000000  47 6f 20 69 73 20 61 6e  20 6f 70 65 6e 20 73 6f  |Go is an open so|
00000010  75 72 63 65 20 70 72 6f  67 72 61 6d 6d 69 6e 67  |urce programming|
00000020  20 6c 61 6e 67 75 61 67  65 2e 0a 57 65 20 65 6e  | language..We en|
00000030  63 6f 75 72 61 67 65 20  61 6c 6c 20 47 6f 20 75  |courage all Go u|
00000040  73 65 72 73 20 74 6f 20  73 75 62 73 63 72 69 62  |sers to subscrib|
00000050  65 20 74 6f 20 67 6f 6c  61 6e 67 2d 61 6e 6e 6f  |e to golang-anno|
00000060  75 6e 63 65 2e                                    |unce.|
```

func Encode 
-----------

```go
func Encode(dst, src []byte) int
```

Encode encodes src into EncodedLen(len(src)) bytes of dst. As a
convenience, it returns the number of bytes written to dst, but this
value is always EncodedLen(len(src)). Encode implements hexadecimal
encoding.

#### [Example]

Code:

```go
src := []byte("Hello Gopher!")

dst := make([]byte, hex.EncodedLen(len(src)))
hex.Encode(dst, src)

fmt.Printf("%s\n", dst)
```

Output:

```go
48656c6c6f20476f7068657221
```

func EncodeToString 
-------------------

```go
func EncodeToString(src []byte) string
```

EncodeToString returns the hexadecimal encoding of src.

#### [Example]

Code:

```go
src := []byte("Hello")
encodedStr := hex.EncodeToString(src)

fmt.Printf("%s\n", encodedStr)
```

Output:

```go
48656c6c6f
```

func EncodedLen 
---------------

```go
func EncodedLen(n int) int
```

EncodedLen returns the length of an encoding of n source bytes.
Specifically, it returns n \* 2.

func NewDecoder 
------------------------------------------------

```go
func NewDecoder(r io.Reader) io.Reader
```

NewDecoder returns an io.Reader that decodes hexadecimal characters from
r. NewDecoder expects that r contain only an even number of hexadecimal
characters.

func NewEncoder 
------------------------------------------------

```go
func NewEncoder(w io.Writer) io.Writer
```

NewEncoder returns an io.Writer that writes lowercase hexadecimal
characters to w.

type InvalidByteError 
---------------------

InvalidByteError values describe errors resulting from an invalid byte
in a hex string.

```go
type InvalidByteError byte
```

### func (InvalidByteError) Error 

```go
func (e InvalidByteError) Error() string
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/encoding/hex/>

