Package utf8
============

-   `import "unicode/utf8"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package utf8 implements functions and constants to support text encoded
in UTF-8. It includes functions to translate between runes and UTF-8
byte sequences. See https://en.wikipedia.org/wiki/UTF-8>

Index 
-----

-   [Constants](#pkg-constants)
-   [func AppendRune(p \[\]byte, r rune) \[\]byte](#AppendRune)
-   [func DecodeLastRune(p \[\]byte) (r rune, size
    int)](#DecodeLastRune)
-   [func DecodeLastRuneInString(s string) (r rune, size
    int)](#DecodeLastRuneInString)
-   [func DecodeRune(p \[\]byte) (r rune, size int)](#DecodeRune)
-   [func DecodeRuneInString(s string) (r rune, size
    int)](#DecodeRuneInString)
-   [func EncodeRune(p \[\]byte, r rune) int](#EncodeRune)
-   [func FullRune(p \[\]byte) bool](#FullRune)
-   [func FullRuneInString(s string) bool](#FullRuneInString)
-   [func RuneCount(p \[\]byte) int](#RuneCount)
-   [func RuneCountInString(s string) (n int)](#RuneCountInString)
-   [func RuneLen(r rune) int](#RuneLen)
-   [func RuneStart(b byte) bool](#RuneStart)
-   [func Valid(p \[\]byte) bool](#Valid)
-   [func ValidRune(r rune) bool](#ValidRune)
-   [func ValidString(s string) bool](#ValidString)

 
### Examples

[AppendRune](#example_AppendRune)

[DecodeLastRune](#example_DecodeLastRune)

[DecodeLastRuneInString](#example_DecodeLastRuneInString)

[DecodeRune](#example_DecodeRune)

[DecodeRuneInString](#example_DecodeRuneInString)

[EncodeRune](#example_EncodeRune)

[EncodeRune (OutOfRange)](#example_EncodeRune_outOfRange)

[FullRune](#example_FullRune)

[FullRuneInString](#example_FullRuneInString)

[RuneCount](#example_RuneCount)

[RuneCountInString](#example_RuneCountInString)

[RuneLen](#example_RuneLen)

[RuneStart](#example_RuneStart)

[Valid](#example_Valid)

[ValidRune](#example_ValidRune)

[ValidString](#example_ValidString)


### Package files

utf8.go

Constants 
---------

Numbers fundamental to the encoding.

```go
const (
    RuneError = '\uFFFD'     // the "error" Rune or "Unicode replacement character"
    RuneSelf  = 0x80         // characters below RuneSelf are represented as themselves in a single byte.
    MaxRune   = '\U0010FFFF' // Maximum valid Unicode code point.
    UTFMax    = 4            // maximum number of bytes of a UTF-8 encoded Unicode character.
)
```

func AppendRune 
------------------------------------------------

```go
func AppendRune(p []byte, r rune) []byte
```

AppendRune appends the UTF-8 encoding of r to the end of p and returns
the extended buffer. If the rune is out of range, it appends the
encoding of RuneError.

#### [Example]

Code:

```go
buf1 := utf8.AppendRune(nil, 0x10000)
buf2 := utf8.AppendRune([]byte("init"), 0x10000)
fmt.Println(string(buf1))
fmt.Println(string(buf2))
```

Output:

```go
𐀀
init𐀀
```

func DecodeLastRune 
-------------------

```go
func DecodeLastRune(p []byte) (r rune, size int)
```

DecodeLastRune unpacks the last UTF-8 encoding in p and returns the rune
and its width in bytes. If p is empty it returns (RuneError, 0).
Otherwise, if the encoding is invalid, it returns (RuneError, 1). Both
are impossible results for correct, non-empty UTF-8.

An encoding is invalid if it is incorrect UTF-8, encodes a rune that is
out of range, or is not the shortest possible UTF-8 encoding for the
value. No other validation is performed.

#### [Example]

Code:

```go
b := []byte("Hello, 世界")

for len(b) > 0 {
    r, size := utf8.DecodeLastRune(b)
    fmt.Printf("%c %v\n", r, size)

    b = b[:len(b)-size]
}
```

Output:

```go
界 3
世 3
  1
, 1
o 1
l 1
l 1
e 1
H 1
```

func DecodeLastRuneInString 
---------------------------

```go
func DecodeLastRuneInString(s string) (r rune, size int)
```

DecodeLastRuneInString is like DecodeLastRune but its input is a string.
If s is empty it returns (RuneError, 0). Otherwise, if the encoding is
invalid, it returns (RuneError, 1). Both are impossible results for
correct, non-empty UTF-8.

An encoding is invalid if it is incorrect UTF-8, encodes a rune that is
out of range, or is not the shortest possible UTF-8 encoding for the
value. No other validation is performed.

#### [Example]

Code:

```go
str := "Hello, 世界"

for len(str) > 0 {
    r, size := utf8.DecodeLastRuneInString(str)
    fmt.Printf("%c %v\n", r, size)

    str = str[:len(str)-size]
}
```

Output:

```go
界 3
世 3
  1
, 1
o 1
l 1
l 1
e 1
H 1
```

func DecodeRune 
---------------

```go
func DecodeRune(p []byte) (r rune, size int)
```

DecodeRune unpacks the first UTF-8 encoding in p and returns the rune
and its width in bytes. If p is empty it returns (RuneError, 0).
Otherwise, if the encoding is invalid, it returns (RuneError, 1). Both
are impossible results for correct, non-empty UTF-8.

An encoding is invalid if it is incorrect UTF-8, encodes a rune that is
out of range, or is not the shortest possible UTF-8 encoding for the
value. No other validation is performed.

#### [Example]

Code:

```go
b := []byte("Hello, 世界")

for len(b) > 0 {
    r, size := utf8.DecodeRune(b)
    fmt.Printf("%c %v\n", r, size)

    b = b[size:]
}
```

Output:

```go
H 1
e 1
l 1
l 1
o 1
, 1
  1
世 3
界 3
```

func DecodeRuneInString 
-----------------------

```go
func DecodeRuneInString(s string) (r rune, size int)
```

DecodeRuneInString is like DecodeRune but its input is a string. If s is
empty it returns (RuneError, 0). Otherwise, if the encoding is invalid,
it returns (RuneError, 1). Both are impossible results for correct,
non-empty UTF-8.

An encoding is invalid if it is incorrect UTF-8, encodes a rune that is
out of range, or is not the shortest possible UTF-8 encoding for the
value. No other validation is performed.

#### [Example]

Code:

```go
str := "Hello, 世界"

for len(str) > 0 {
    r, size := utf8.DecodeRuneInString(str)
    fmt.Printf("%c %v\n", r, size)

    str = str[size:]
}
```

Output:

```go
H 1
e 1
l 1
l 1
o 1
, 1
  1
世 3
界 3
```

func EncodeRune 
---------------

```go
func EncodeRune(p []byte, r rune) int
```

EncodeRune writes into p (which must be large enough) the UTF-8 encoding
of the rune. If the rune is out of range, it writes the encoding of
RuneError. It returns the number of bytes written.

#### [Example]

Code:

```go
r := '世'
buf := make([]byte, 3)

n := utf8.EncodeRune(buf, r)

fmt.Println(buf)
fmt.Println(n)
```

Output:

```go
[228 184 150]
3
```

#### [Example (OutOfRange)]

Code:

```go
runes := []rune{
    // Less than 0, out of range.
    -1,
    // Greater than 0x10FFFF, out of range.
    0x110000,
    // The Unicode replacement character.
    utf8.RuneError,
}
for i, c := range runes {
    buf := make([]byte, 3)
    size := utf8.EncodeRune(buf, c)
    fmt.Printf("%d: %d %[2]s %d\n", i, buf, size)
}
```

Output:

```go
0: [239 191 189] � 3
1: [239 191 189] � 3
2: [239 191 189] � 3
```

func FullRune 
-------------

```go
func FullRune(p []byte) bool
```

FullRune reports whether the bytes in p begin with a full UTF-8 encoding
of a rune. An invalid encoding is considered a full Rune since it will
convert as a width-1 error rune.

#### [Example]

Code:

```go
buf := []byte{228, 184, 150} // 世
fmt.Println(utf8.FullRune(buf))
fmt.Println(utf8.FullRune(buf[:2]))
```

Output:

```go
true
false
```

func FullRuneInString 
---------------------

```go
func FullRuneInString(s string) bool
```

FullRuneInString is like FullRune but its input is a string.

#### [Example]

Code:

```go
str := "世"
fmt.Println(utf8.FullRuneInString(str))
fmt.Println(utf8.FullRuneInString(str[:2]))
```

Output:

```go
true
false
```

func RuneCount 
--------------

```go
func RuneCount(p []byte) int
```

RuneCount returns the number of runes in p. Erroneous and short
encodings are treated as single runes of width 1 byte.

#### [Example]

Code:

```go
buf := []byte("Hello, 世界")
fmt.Println("bytes =", len(buf))
fmt.Println("runes =", utf8.RuneCount(buf))
```

Output:

```go
bytes = 13
runes = 9
```

func RuneCountInString 
----------------------

```go
func RuneCountInString(s string) (n int)
```

RuneCountInString is like RuneCount but its input is a string.

#### [Example]

Code:

```go
str := "Hello, 世界"
fmt.Println("bytes =", len(str))
fmt.Println("runes =", utf8.RuneCountInString(str))
```

Output:

```go
bytes = 13
runes = 9
```

func RuneLen 
------------

```go
func RuneLen(r rune) int
```

RuneLen returns the number of bytes required to encode the rune. It
returns -1 if the rune is not a valid value to encode in UTF-8.

#### [Example]

Code:

```go
fmt.Println(utf8.RuneLen('a'))
fmt.Println(utf8.RuneLen('界'))
```

Output:

```go
1
3
```

func RuneStart 
--------------

```go
func RuneStart(b byte) bool
```

RuneStart reports whether the byte could be the first byte of an
encoded, possibly invalid rune. Second and subsequent bytes always have
the top two bits set to 10.

#### [Example]

Code:

```go
buf := []byte("a界")
fmt.Println(utf8.RuneStart(buf[0]))
fmt.Println(utf8.RuneStart(buf[1]))
fmt.Println(utf8.RuneStart(buf[2]))
```

Output:

```go
true
true
false
```

func Valid 
----------

```go
func Valid(p []byte) bool
```

Valid reports whether p consists entirely of valid UTF-8-encoded runes.

#### [Example]

Code:

```go
valid := []byte("Hello, 世界")
invalid := []byte{0xff, 0xfe, 0xfd}

fmt.Println(utf8.Valid(valid))
fmt.Println(utf8.Valid(invalid))
```

Output:

```go
true
false
```

func ValidRune 
---------------------------------------------

```go
func ValidRune(r rune) bool
```

ValidRune reports whether r can be legally encoded as UTF-8. Code points
that are out of range or a surrogate half are illegal.

#### [Example]

Code:

```go
valid := 'a'
invalid := rune(0xfffffff)

fmt.Println(utf8.ValidRune(valid))
fmt.Println(utf8.ValidRune(invalid))
```

Output:

```go
true
false
```

func ValidString 
----------------

```go
func ValidString(s string) bool
```

ValidString reports whether s consists entirely of valid UTF-8-encoded
runes.

#### [Example]

Code:

```go
valid := "Hello, 世界"
invalid := string([]byte{0xff, 0xfe, 0xfd})

fmt.Println(utf8.ValidString(valid))
fmt.Println(utf8.ValidString(invalid))
```

Output:

```go
true
false
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/unicode/utf8/>

