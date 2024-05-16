Package utf16
=============

-   `import "unicode/utf16"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)

Overview 
--------

Package utf16 implements encoding and decoding of UTF-16 sequences.

Index 
-----

-   [func AppendRune(a \[\]uint16, r rune) \[\]uint16](#AppendRune)
-   [func Decode(s \[\]uint16) \[\]rune](#Decode)
-   [func DecodeRune(r1, r2 rune) rune](#DecodeRune)
-   [func Encode(s \[\]rune) \[\]uint16](#Encode)
-   [func EncodeRune(r rune) (r1, r2 rune)](#EncodeRune)
-   [func IsSurrogate(r rune) bool](#IsSurrogate)

### Package files

utf16.go

func AppendRune 
------------------------------------------------

```go
func AppendRune(a []uint16, r rune) []uint16
```

AppendRune appends the UTF-16 encoding of the Unicode code point r to
the end of p and returns the extended buffer. If the rune is not a valid
Unicode code point, it appends the encoding of U+FFFD.

func Decode 
-----------

```go
func Decode(s []uint16) []rune
```

Decode returns the Unicode code point sequence represented by the UTF-16
encoding s.

func DecodeRune 
---------------

```go
func DecodeRune(r1, r2 rune) rune
```

DecodeRune returns the UTF-16 decoding of a surrogate pair. If the pair
is not a valid UTF-16 surrogate pair, DecodeRune returns the Unicode
replacement code point U+FFFD.

func Encode 
-----------

```go
func Encode(s []rune) []uint16
```

Encode returns the UTF-16 encoding of the Unicode code point sequence s.

func EncodeRune 
---------------

```go
func EncodeRune(r rune) (r1, r2 rune)
```

EncodeRune returns the UTF-16 surrogate pair r1, r2 for the given rune.
If the rune is not a valid Unicode code point or does not need encoding,
EncodeRune returns U+FFFD, U+FFFD.

func IsSurrogate 
----------------

```go
func IsSurrogate(r rune) bool
```

IsSurrogate reports whether the specified Unicode code point can appear
in a surrogate pair.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/unicode/utf16/>

