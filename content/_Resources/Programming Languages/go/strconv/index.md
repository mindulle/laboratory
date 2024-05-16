Package strconv
===============

-   `import "strconv"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package strconv implements conversions to and from string
representations of basic data types.

### Numeric Conversions 

The most common numeric conversions are Atoi (string to int) and Itoa
(int to string).

```go
i, err := strconv.Atoi("-42")
s := strconv.Itoa(-42)
```

These assume decimal and the Go int type.

[ParseBool](#ParseBool), [ParseFloat](#ParseFloat),
[ParseInt](#ParseInt), and [ParseUint](#ParseUint) convert strings to
values:

```go
b, err := strconv.ParseBool("true")
f, err := strconv.ParseFloat("3.1415", 64)
i, err := strconv.ParseInt("-42", 10, 64)
u, err := strconv.ParseUint("42", 10, 64)
```

The parse functions return the widest type (float64, int64, and uint64),
but if the size argument specifies a narrower width the result can be
converted to that narrower type without data loss:

```go
s := "2147483647" // biggest int32
i64, err := strconv.ParseInt(s, 10, 32)
...
i := int32(i64)
```

[FormatBool](#FormatBool), [FormatFloat](#FormatFloat),
[FormatInt](#FormatInt), and [FormatUint](#FormatUint) convert values to
strings:

```go
s := strconv.FormatBool(true)
s := strconv.FormatFloat(3.1415, 'E', -1, 64)
s := strconv.FormatInt(-42, 16)
s := strconv.FormatUint(42, 16)
```

[AppendBool](#AppendBool), [AppendFloat](#AppendFloat),
[AppendInt](#AppendInt), and [AppendUint](#AppendUint) are similar but
append the formatted value to a destination slice.

### String Conversions 

[Quote](#Quote) and [QuoteToASCII](#QuoteToASCII) convert strings to
quoted Go string literals. The latter guarantees that the result is an
ASCII string, by escaping any non-ASCII Unicode with \\u:

```go
q := strconv.Quote("Hello, 世界")
q := strconv.QuoteToASCII("Hello, 世界")
```

[QuoteRune](#QuoteRune) and [QuoteRuneToASCII](#QuoteRuneToASCII) are
similar but accept runes and return quoted Go rune literals.

[Unquote](#Unquote) and [UnquoteChar](#UnquoteChar) unquote Go string
and rune literals.

Index 
-----

-   [Constants](#pkg-constants)
-   [Variables](#pkg-variables)
-   [func AppendBool(dst \[\]byte, b bool) \[\]byte](#AppendBool)
-   [func AppendFloat(dst \[\]byte, f float64, fmt byte, prec, bitSize
    int) \[\]byte](#AppendFloat)
-   [func AppendInt(dst \[\]byte, i int64, base int)
    \[\]byte](#AppendInt)
-   [func AppendQuote(dst \[\]byte, s string) \[\]byte](#AppendQuote)
-   [func AppendQuoteRune(dst \[\]byte, r rune)
    \[\]byte](#AppendQuoteRune)
-   [func AppendQuoteRuneToASCII(dst \[\]byte, r rune)
    \[\]byte](#AppendQuoteRuneToASCII)
-   [func AppendQuoteRuneToGraphic(dst \[\]byte, r rune)
    \[\]byte](#AppendQuoteRuneToGraphic)
-   [func AppendQuoteToASCII(dst \[\]byte, s string)
    \[\]byte](#AppendQuoteToASCII)
-   [func AppendQuoteToGraphic(dst \[\]byte, s string)
    \[\]byte](#AppendQuoteToGraphic)
-   [func AppendUint(dst \[\]byte, i uint64, base int)
    \[\]byte](#AppendUint)
-   [func Atoi(s string) (int, error)](#Atoi)
-   [func CanBackquote(s string) bool](#CanBackquote)
-   [func FormatBool(b bool) string](#FormatBool)
-   [func FormatComplex(c complex128, fmt byte, prec, bitSize int)
    string](#FormatComplex)
-   [func FormatFloat(f float64, fmt byte, prec, bitSize int)
    string](#FormatFloat)
-   [func FormatInt(i int64, base int) string](#FormatInt)
-   [func FormatUint(i uint64, base int) string](#FormatUint)
-   [func IsGraphic(r rune) bool](#IsGraphic)
-   [func IsPrint(r rune) bool](#IsPrint)
-   [func Itoa(i int) string](#Itoa)
-   [func ParseBool(str string) (bool, error)](#ParseBool)
-   [func ParseComplex(s string, bitSize int) (complex128,
    error)](#ParseComplex)
-   [func ParseFloat(s string, bitSize int) (float64,
    error)](#ParseFloat)
-   [func ParseInt(s string, base int, bitSize int) (i int64, err
    error)](#ParseInt)
-   [func ParseUint(s string, base int, bitSize int) (uint64,
    error)](#ParseUint)
-   [func Quote(s string) string](#Quote)
-   [func QuoteRune(r rune) string](#QuoteRune)
-   [func QuoteRuneToASCII(r rune) string](#QuoteRuneToASCII)
-   [func QuoteRuneToGraphic(r rune) string](#QuoteRuneToGraphic)
-   [func QuoteToASCII(s string) string](#QuoteToASCII)
-   [func QuoteToGraphic(s string) string](#QuoteToGraphic)
-   [func QuotedPrefix(s string) (string, error)](#QuotedPrefix)
-   [func Unquote(s string) (string, error)](#Unquote)
-   [func UnquoteChar(s string, quote byte) (value rune, multibyte bool,
    tail string, err error)](#UnquoteChar)
-   [type NumError](#NumError)
-   [func (e \*NumError) Error() string](#NumError.Error)
-   [func (e \*NumError) Unwrap() error](#NumError.Unwrap)

 
### Examples

[AppendBool](#example_AppendBool)

[AppendFloat](#example_AppendFloat)

[AppendInt](#example_AppendInt)

[AppendQuote](#example_AppendQuote)

[AppendQuoteRune](#example_AppendQuoteRune)

[AppendQuoteRuneToASCII](#example_AppendQuoteRuneToASCII)

[AppendQuoteToASCII](#example_AppendQuoteToASCII)

[AppendUint](#example_AppendUint)

[Atoi](#example_Atoi)

[CanBackquote](#example_CanBackquote)

[FormatBool](#example_FormatBool)

[FormatFloat](#example_FormatFloat)

[FormatInt](#example_FormatInt)

[FormatUint](#example_FormatUint)

[IsGraphic](#example_IsGraphic)

[IsPrint](#example_IsPrint)

[Itoa](#example_Itoa)

[NumError](#example_NumError)

[ParseBool](#example_ParseBool)

[ParseFloat](#example_ParseFloat)

[ParseInt](#example_ParseInt)

[ParseUint](#example_ParseUint)

[Quote](#example_Quote)

[QuoteRune](#example_QuoteRune)

[QuoteRuneToASCII](#example_QuoteRuneToASCII)

[QuoteRuneToGraphic](#example_QuoteRuneToGraphic)

[QuoteToASCII](#example_QuoteToASCII)

[QuoteToGraphic](#example_QuoteToGraphic)

[Unquote](#example_Unquote)

[UnquoteChar](#example_UnquoteChar)


### Package files

atob.go atoc.go atof.go atoi.go bytealg.go ctoa.go decimal.go doc.go
eisel\_lemire.go ftoa.go ftoaryu.go isprint.go itoa.go quote.go

Constants 
---------

IntSize is the size in bits of an int or uint value.

```go
const IntSize = intSize
```

Variables 
---------

ErrRange indicates that a value is out of range for the target type.

```go
var ErrRange = errors.New("value out of range")
```

ErrSyntax indicates that a value does not have the right syntax for the
target type.

```go
var ErrSyntax = errors.New("invalid syntax")
```

func AppendBool 
---------------

```go
func AppendBool(dst []byte, b bool) []byte
```

AppendBool appends \"true\" or \"false\", according to the value of b,
to dst and returns the extended buffer.

#### [Example]

Code:

```go
b := []byte("bool:")
b = strconv.AppendBool(b, true)
fmt.Println(string(b))
```

Output:

```go
bool:true
```

func AppendFloat 
----------------

```go
func AppendFloat(dst []byte, f float64, fmt byte, prec, bitSize int) []byte
```

AppendFloat appends the string form of the floating-point number f, as
generated by FormatFloat, to dst and returns the extended buffer.

#### [Example]

Code:

```go
b32 := []byte("float32:")
b32 = strconv.AppendFloat(b32, 3.1415926535, 'E', -1, 32)
fmt.Println(string(b32))

b64 := []byte("float64:")
b64 = strconv.AppendFloat(b64, 3.1415926535, 'E', -1, 64)
fmt.Println(string(b64))
```

Output:

```go
float32:3.1415927E+00
float64:3.1415926535E+00
```

func AppendInt 
--------------

```go
func AppendInt(dst []byte, i int64, base int) []byte
```

AppendInt appends the string form of the integer i, as generated by
FormatInt, to dst and returns the extended buffer.

#### [Example]

Code:

```go
b10 := []byte("int (base 10):")
b10 = strconv.AppendInt(b10, -42, 10)
fmt.Println(string(b10))

b16 := []byte("int (base 16):")
b16 = strconv.AppendInt(b16, -42, 16)
fmt.Println(string(b16))
```

Output:

```go
int (base 10):-42
int (base 16):-2a
```

func AppendQuote 
----------------

```go
func AppendQuote(dst []byte, s string) []byte
```

AppendQuote appends a double-quoted Go string literal representing s, as
generated by Quote, to dst and returns the extended buffer.

#### [Example]

Code:

```go
b := []byte("quote:")
b = strconv.AppendQuote(b, `"Fran & Freddie's Diner"`)
fmt.Println(string(b))
```

Output:

```go
quote:"\"Fran & Freddie's Diner\""
```

func AppendQuoteRune 
--------------------

```go
func AppendQuoteRune(dst []byte, r rune) []byte
```

AppendQuoteRune appends a single-quoted Go character literal
representing the rune, as generated by QuoteRune, to dst and returns the
extended buffer.

#### [Example]

Code:

```go
b := []byte("rune:")
b = strconv.AppendQuoteRune(b, '☺')
fmt.Println(string(b))
```

Output:

```go
rune:'☺'
```

func AppendQuoteRuneToASCII 
---------------------------

```go
func AppendQuoteRuneToASCII(dst []byte, r rune) []byte
```

AppendQuoteRuneToASCII appends a single-quoted Go character literal
representing the rune, as generated by QuoteRuneToASCII, to dst and
returns the extended buffer.

#### [Example]

Code:

```go
b := []byte("rune (ascii):")
b = strconv.AppendQuoteRuneToASCII(b, '☺')
fmt.Println(string(b))
```

Output:

```go
rune (ascii):'\u263a'
```

func AppendQuoteRuneToGraphic 
------------------------------------------------------------

```go
func AppendQuoteRuneToGraphic(dst []byte, r rune) []byte
```

AppendQuoteRuneToGraphic appends a single-quoted Go character literal
representing the rune, as generated by QuoteRuneToGraphic, to dst and
returns the extended buffer.

func AppendQuoteToASCII 
-----------------------

```go
func AppendQuoteToASCII(dst []byte, s string) []byte
```

AppendQuoteToASCII appends a double-quoted Go string literal
representing s, as generated by QuoteToASCII, to dst and returns the
extended buffer.

#### [Example]

Code:

```go
b := []byte("quote (ascii):")
b = strconv.AppendQuoteToASCII(b, `"Fran & Freddie's Diner"`)
fmt.Println(string(b))
```

Output:

```go
quote (ascii):"\"Fran & Freddie's Diner\""
```

func AppendQuoteToGraphic 
--------------------------------------------------------

```go
func AppendQuoteToGraphic(dst []byte, s string) []byte
```

AppendQuoteToGraphic appends a double-quoted Go string literal
representing s, as generated by QuoteToGraphic, to dst and returns the
extended buffer.

func AppendUint 
---------------

```go
func AppendUint(dst []byte, i uint64, base int) []byte
```

AppendUint appends the string form of the unsigned integer i, as
generated by FormatUint, to dst and returns the extended buffer.

#### [Example]

Code:

```go
b10 := []byte("uint (base 10):")
b10 = strconv.AppendUint(b10, 42, 10)
fmt.Println(string(b10))

b16 := []byte("uint (base 16):")
b16 = strconv.AppendUint(b16, 42, 16)
fmt.Println(string(b16))
```

Output:

```go
uint (base 10):42
uint (base 16):2a
```

func Atoi 
---------

```go
func Atoi(s string) (int, error)
```

Atoi is equivalent to ParseInt(s, 10, 0), converted to type int.

#### [Example]

Code:

```go
v := "10"
if s, err := strconv.Atoi(v); err == nil {
    fmt.Printf("%T, %v", s, s)
}
```

Output:

```go
int, 10
```

func CanBackquote 
-----------------

```go
func CanBackquote(s string) bool
```

CanBackquote reports whether the string s can be represented unchanged
as a single-line backquoted string without control characters other than
tab.

#### [Example]

Code:

```go
fmt.Println(strconv.CanBackquote("Fran & Freddie's Diner ☺"))
fmt.Println(strconv.CanBackquote("`can't backquote this`"))
```

Output:

```go
true
false
```

func FormatBool 
---------------

```go
func FormatBool(b bool) string
```

FormatBool returns \"true\" or \"false\" according to the value of b.

#### [Example]

Code:

```go
v := true
s := strconv.FormatBool(v)
fmt.Printf("%T, %v\n", s, s)
```

Output:

```go
string, true
```

func FormatComplex 
---------------------------------------------------

```go
func FormatComplex(c complex128, fmt byte, prec, bitSize int) string
```

FormatComplex converts the complex number c to a string of the form
(a+bi) where a and b are the real and imaginary parts, formatted
according to the format fmt and precision prec.

The format fmt and precision prec have the same meaning as in
FormatFloat. It rounds the result assuming that the original was
obtained from a complex value of bitSize bits, which must be 64 for
complex64 and 128 for complex128.

func FormatFloat 
----------------

```go
func FormatFloat(f float64, fmt byte, prec, bitSize int) string
```

FormatFloat converts the floating-point number f to a string, according
to the format fmt and precision prec. It rounds the result assuming that
the original was obtained from a floating-point value of bitSize bits
(32 for float32, 64 for float64).

The format fmt is one of \'b\' (-ddddp±ddd, a binary exponent), \'e\'
(-d.dddde±dd, a decimal exponent), \'E\' (-d.ddddE±dd, a decimal
exponent), \'f\' (-ddd.dddd, no exponent), \'g\' (\'e\' for large
exponents, \'f\' otherwise), \'G\' (\'E\' for large exponents, \'f\'
otherwise), \'x\' (-0xd.ddddp±ddd, a hexadecimal fraction and binary
exponent), or \'X\' (-0Xd.ddddP±ddd, a hexadecimal fraction and binary
exponent).

The precision prec controls the number of digits (excluding the
exponent) printed by the \'e\', \'E\', \'f\', \'g\', \'G\', \'x\', and
\'X\' formats. For \'e\', \'E\', \'f\', \'x\', and \'X\', it is the
number of digits after the decimal point. For \'g\' and \'G\' it is the
maximum number of significant digits (trailing zeros are removed). The
special precision -1 uses the smallest number of digits necessary such
that ParseFloat will return f exactly.

#### [Example]

Code:

```go
v := 3.1415926535

s32 := strconv.FormatFloat(v, 'E', -1, 32)
fmt.Printf("%T, %v\n", s32, s32)

s64 := strconv.FormatFloat(v, 'E', -1, 64)
fmt.Printf("%T, %v\n", s64, s64)

// fmt.Println uses these arguments to print floats
fmt64 := strconv.FormatFloat(v, 'g', -1, 64)
fmt.Printf("%T, %v\n", fmt64, fmt64)
```

Output:

```go
string, 3.1415927E+00
string, 3.1415926535E+00
string, 3.1415926535
```

func FormatInt 
--------------

```go
func FormatInt(i int64, base int) string
```

FormatInt returns the string representation of i in the given base, for
2 \<= base \<= 36. The result uses the lower-case letters \'a\' to \'z\'
for digit values \>= 10.

#### [Example]

Code:

```go
v := int64(-42)

s10 := strconv.FormatInt(v, 10)
fmt.Printf("%T, %v\n", s10, s10)

s16 := strconv.FormatInt(v, 16)
fmt.Printf("%T, %v\n", s16, s16)
```

Output:

```go
string, -42
string, -2a
```

func FormatUint 
---------------

```go
func FormatUint(i uint64, base int) string
```

FormatUint returns the string representation of i in the given base, for
2 \<= base \<= 36. The result uses the lower-case letters \'a\' to \'z\'
for digit values \>= 10.

#### [Example]

Code:

```go
v := uint64(42)

s10 := strconv.FormatUint(v, 10)
fmt.Printf("%T, %v\n", s10, s10)

s16 := strconv.FormatUint(v, 16)
fmt.Printf("%T, %v\n", s16, s16)
```

Output:

```go
string, 42
string, 2a
```

func IsGraphic 
---------------------------------------------

```go
func IsGraphic(r rune) bool
```

IsGraphic reports whether the rune is defined as a Graphic by Unicode.
Such characters include letters, marks, numbers, punctuation, symbols,
and spaces, from categories L, M, N, P, S, and Zs.

#### [Example]

Code:

```go
shamrock := strconv.IsGraphic('☘')
fmt.Println(shamrock)

a := strconv.IsGraphic('a')
fmt.Println(a)

bel := strconv.IsGraphic('\007')
fmt.Println(bel)
```

Output:

```go
true
true
false
```

func IsPrint 
------------

```go
func IsPrint(r rune) bool
```

IsPrint reports whether the rune is defined as printable by Go, with the
same definition as unicode.IsPrint: letters, numbers, punctuation,
symbols and ASCII space.

#### [Example]

Code:

```go
c := strconv.IsPrint('\u263a')
fmt.Println(c)

bel := strconv.IsPrint('\007')
fmt.Println(bel)
```

Output:

```go
true
false
```

func Itoa 
---------

```go
func Itoa(i int) string
```

Itoa is equivalent to FormatInt(int64(i), 10).

#### [Example]

Code:

```go
i := 10
s := strconv.Itoa(i)
fmt.Printf("%T, %v\n", s, s)
```

Output:

```go
string, 10
```

func ParseBool 
--------------

```go
func ParseBool(str string) (bool, error)
```

ParseBool returns the boolean value represented by the string. It
accepts 1, t, T, TRUE, true, True, 0, f, F, FALSE, false, False. Any
other value returns an error.

#### [Example]

Code:

```go
v := "true"
if s, err := strconv.ParseBool(v); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}
```

Output:

```go
bool, true
```

func ParseComplex 
--------------------------------------------------

```go
func ParseComplex(s string, bitSize int) (complex128, error)
```

ParseComplex converts the string s to a complex number with the
precision specified by bitSize: 64 for complex64, or 128 for complex128.
When bitSize=64, the result still has type complex128, but it will be
convertible to complex64 without changing its value.

The number represented by s must be of the form N, Ni, or N±Ni, where N
stands for a floating-point number as recognized by ParseFloat, and i is
the imaginary component. If the second N is unsigned, a + sign is
required between the two components as indicated by the ±. If the second
N is NaN, only a + sign is accepted. The form may be parenthesized and
cannot contain any spaces. The resulting complex number consists of the
two components converted by ParseFloat.

The errors that ParseComplex returns have concrete type \*NumError and
include err.Num = s.

If s is not syntactically well-formed, ParseComplex returns err.Err =
ErrSyntax.

If s is syntactically well-formed but either component is more than 1/2
ULP away from the largest floating point number of the given
component\'s size, ParseComplex returns err.Err = ErrRange and c = ±Inf
for the respective component.

func ParseFloat 
---------------

```go
func ParseFloat(s string, bitSize int) (float64, error)
```

ParseFloat converts the string s to a floating-point number with the
precision specified by bitSize: 32 for float32, or 64 for float64. When
bitSize=32, the result still has type float64, but it will be
convertible to float32 without changing its value.

ParseFloat accepts decimal and hexadecimal floating-point numbers as
defined by the Go syntax for [floating-point
literals](https://go.dev/ref/spec#Floating-point_literals). If s is
well-formed and near a valid floating-point number, ParseFloat returns
the nearest floating-point number rounded using IEEE754 unbiased
rounding. (Parsing a hexadecimal floating-point value only rounds when
there are more bits in the hexadecimal representation than will fit in
the mantissa.)

The errors that ParseFloat returns have concrete type \*NumError and
include err.Num = s.

If s is not syntactically well-formed, ParseFloat returns err.Err =
ErrSyntax.

If s is syntactically well-formed but is more than 1/2 ULP away from the
largest floating point number of the given size, ParseFloat returns f =
±Inf, err.Err = ErrRange.

ParseFloat recognizes the string \"NaN\", and the (possibly signed)
strings \"Inf\" and \"Infinity\" as their respective special floating
point values. It ignores case when matching.

#### [Example]

Code:

```go
v := "3.1415926535"
if s, err := strconv.ParseFloat(v, 32); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}
if s, err := strconv.ParseFloat(v, 64); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}
if s, err := strconv.ParseFloat("NaN", 32); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}
// ParseFloat is case insensitive
if s, err := strconv.ParseFloat("nan", 32); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}
if s, err := strconv.ParseFloat("inf", 32); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}
if s, err := strconv.ParseFloat("+Inf", 32); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}
if s, err := strconv.ParseFloat("-Inf", 32); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}
if s, err := strconv.ParseFloat("-0", 32); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}
if s, err := strconv.ParseFloat("+0", 32); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}
```

Output:

```go
float64, 3.1415927410125732
float64, 3.1415926535
float64, NaN
float64, NaN
float64, +Inf
float64, +Inf
float64, -Inf
float64, -0
float64, 0
```

func ParseInt 
-------------

```go
func ParseInt(s string, base int, bitSize int) (i int64, err error)
```

ParseInt interprets a string s in the given base (0, 2 to 36) and bit
size (0 to 64) and returns the corresponding value i.

The string may begin with a leading sign: \"+\" or \"-\".

If the base argument is 0, the true base is implied by the string\'s
prefix following the sign (if present): 2 for \"0b\", 8 for \"0\" or
\"0o\", 16 for \"0x\", and 10 otherwise. Also, for argument base 0 only,
underscore characters are permitted as defined by the Go syntax for
[integer literals](https://go.dev/ref/spec#Integer_literals).

The bitSize argument specifies the integer type that the result must fit
into. Bit sizes 0, 8, 16, 32, and 64 correspond to int, int8, int16,
int32, and int64. If bitSize is below 0 or above 64, an error is
returned.

The errors that ParseInt returns have concrete type \*NumError and
include err.Num = s. If s is empty or contains invalid digits, err.Err =
ErrSyntax and the returned value is 0; if the value corresponding to s
cannot be represented by a signed integer of the given size, err.Err =
ErrRange and the returned value is the maximum magnitude integer of the
appropriate bitSize and sign.

#### [Example]

Code:

```go
v32 := "-354634382"
if s, err := strconv.ParseInt(v32, 10, 32); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}
if s, err := strconv.ParseInt(v32, 16, 32); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}

v64 := "-3546343826724305832"
if s, err := strconv.ParseInt(v64, 10, 64); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}
if s, err := strconv.ParseInt(v64, 16, 64); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}
```

Output:

```go
int64, -354634382
int64, -3546343826724305832
```

func ParseUint 
--------------

```go
func ParseUint(s string, base int, bitSize int) (uint64, error)
```

ParseUint is like ParseInt but for unsigned numbers.

A sign prefix is not permitted.

#### [Example]

Code:

```go
v := "42"
if s, err := strconv.ParseUint(v, 10, 32); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}
if s, err := strconv.ParseUint(v, 10, 64); err == nil {
    fmt.Printf("%T, %v\n", s, s)
}
```

Output:

```go
uint64, 42
uint64, 42
```

func Quote 
----------

```go
func Quote(s string) string
```

Quote returns a double-quoted Go string literal representing s. The
returned string uses Go escape sequences (\\t, \\n, \\xFF, \\u0100) for
control characters and non-printable characters as defined by IsPrint.

#### [Example]

Code:

```go
// This string literal contains a tab character.
s := strconv.Quote(`"Fran & Freddie's Diner ☺"`)
fmt.Println(s)
```

Output:

```go
"\"Fran & Freddie's Diner\t☺\""
```

func QuoteRune 
--------------

```go
func QuoteRune(r rune) string
```

QuoteRune returns a single-quoted Go character literal representing the
rune. The returned string uses Go escape sequences (\\t, \\n, \\xFF,
\\u0100) for control characters and non-printable characters as defined
by IsPrint. If r is not a valid Unicode code point, it is interpreted as
the Unicode replacement character U+FFFD.

#### [Example]

Code:

```go
s := strconv.QuoteRune('☺')
fmt.Println(s)
```

Output:

```go
'☺'
```

func QuoteRuneToASCII 
---------------------

```go
func QuoteRuneToASCII(r rune) string
```

QuoteRuneToASCII returns a single-quoted Go character literal
representing the rune. The returned string uses Go escape sequences
(\\t, \\n, \\xFF, \\u0100) for non-ASCII characters and non-printable
characters as defined by IsPrint. If r is not a valid Unicode code
point, it is interpreted as the Unicode replacement character U+FFFD.

#### [Example]

Code:

```go
s := strconv.QuoteRuneToASCII('☺')
fmt.Println(s)
```

Output:

```go
'\u263a'
```

func QuoteRuneToGraphic 
------------------------------------------------------

```go
func QuoteRuneToGraphic(r rune) string
```

QuoteRuneToGraphic returns a single-quoted Go character literal
representing the rune. If the rune is not a Unicode graphic character,
as defined by IsGraphic, the returned string will use a Go escape
sequence (\\t, \\n, \\xFF, \\u0100). If r is not a valid Unicode code
point, it is interpreted as the Unicode replacement character U+FFFD.

#### [Example]

Code:

```go
s := strconv.QuoteRuneToGraphic('☺')
fmt.Println(s)

s = strconv.QuoteRuneToGraphic('\u263a')
fmt.Println(s)

s = strconv.QuoteRuneToGraphic('\u000a')
fmt.Println(s)

s = strconv.QuoteRuneToGraphic('    ') // tab character
fmt.Println(s)
```

Output:

```go
'☺'
'☺'
'\n'
'\t'
```

func QuoteToASCII 
-----------------

```go
func QuoteToASCII(s string) string
```

QuoteToASCII returns a double-quoted Go string literal representing s.
The returned string uses Go escape sequences (\\t, \\n, \\xFF, \\u0100)
for non-ASCII characters and non-printable characters as defined by
IsPrint.

#### [Example]

Code:

```go
// This string literal contains a tab character.
s := strconv.QuoteToASCII(`"Fran & Freddie's Diner  ☺"`)
fmt.Println(s)
```

Output:

```go
"\"Fran & Freddie's Diner\t\u263a\""
```

func QuoteToGraphic 
--------------------------------------------------

```go
func QuoteToGraphic(s string) string
```

QuoteToGraphic returns a double-quoted Go string literal representing s.
The returned string leaves Unicode graphic characters, as defined by
IsGraphic, unchanged and uses Go escape sequences (\\t, \\n, \\xFF,
\\u0100) for non-graphic characters.

#### [Example]

Code:

```go
s := strconv.QuoteToGraphic("☺")
fmt.Println(s)

// This string literal contains a tab character.
s = strconv.QuoteToGraphic("This is a \u263a    \u000a")
fmt.Println(s)

s = strconv.QuoteToGraphic(`" This is a ☺ \n "`)
fmt.Println(s)
```

Output:

```go
"☺"
"This is a ☺\t\n"
"\" This is a ☺ \\n \""
```

func QuotedPrefix 
--------------------------------------------------

```go
func QuotedPrefix(s string) (string, error)
```

QuotedPrefix returns the quoted string (as understood by Unquote) at the
prefix of s. If s does not start with a valid quoted string,
QuotedPrefix returns an error.

func Unquote 
------------

```go
func Unquote(s string) (string, error)
```

Unquote interprets s as a single-quoted, double-quoted, or backquoted Go
string literal, returning the string value that s quotes. (If s is
single-quoted, it would be a Go character literal; Unquote returns the
corresponding one-character string.)

#### [Example]

Code:

```go
s, err := strconv.Unquote("You can't unquote a string without quotes")
fmt.Printf("%q, %v\n", s, err)
s, err = strconv.Unquote("\"The string must be either double-quoted\"")
fmt.Printf("%q, %v\n", s, err)
s, err = strconv.Unquote("`or backquoted.`")
fmt.Printf("%q, %v\n", s, err)
s, err = strconv.Unquote("'\u263a'") // single character only allowed in single quotes
fmt.Printf("%q, %v\n", s, err)
s, err = strconv.Unquote("'\u2639\u2639'")
fmt.Printf("%q, %v\n", s, err)
```

Output:

```go
"", invalid syntax
"The string must be either double-quoted", <nil>
"or backquoted.", <nil>
"☺", <nil>
"", invalid syntax
```

func UnquoteChar 
----------------

```go
func UnquoteChar(s string, quote byte) (value rune, multibyte bool, tail string, err error)
```

UnquoteChar decodes the first character or byte in the escaped string or
character literal represented by the string s. It returns four values:

1.  value, the decoded Unicode code point or byte value;
2.  multibyte, a boolean indicating whether the decoded character
    requires a multibyte UTF-8 representation;
3.  tail, the remainder of the string after the character; and
4.  an error that will be nil if the character is syntactically valid.

The second argument, quote, specifies the type of literal being parsed
and therefore which escaped quote character is permitted. If set to a
single quote, it permits the sequence \\\' and disallows unescaped \'.
If set to a double quote, it permits \\\" and disallows unescaped \". If
set to zero, it does not permit either escape and allows both quote
characters to appear unescaped.

#### [Example]

Code:

```go
v, mb, t, err := strconv.UnquoteChar(`\"Fran & Freddie's Diner\"`, '"')
if err != nil {
    log.Fatal(err)
}

fmt.Println("value:", string(v))
fmt.Println("multibyte:", mb)
fmt.Println("tail:", t)
```

Output:

```go
value: "
multibyte: false
tail: Fran & Freddie's Diner\"
```

type NumError 
-------------

A NumError records a failed conversion.

```go
type NumError struct {
    Func string // the failing function (ParseBool, ParseInt, ParseUint, ParseFloat, ParseComplex)
    Num  string // the input
    Err  error  // the reason the conversion failed (e.g. ErrRange, ErrSyntax, etc.)
}
```

#### [Example]

Code:

```go
str := "Not a number"
if _, err := strconv.ParseFloat(str, 64); err != nil {
    e := err.(*strconv.NumError)
    fmt.Println("Func:", e.Func)
    fmt.Println("Num:", e.Num)
    fmt.Println("Err:", e.Err)
    fmt.Println(err)
}
```

Output:

```go
Func: ParseFloat
Num: Not a number
Err: invalid syntax
strconv.ParseFloat: parsing "Not a number": invalid syntax
```

### func (\*NumError) Error 

```go
func (e *NumError) Error() string
```

### func (\*NumError) Unwrap 

```go
func (e *NumError) Unwrap() error
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/strconv/>

