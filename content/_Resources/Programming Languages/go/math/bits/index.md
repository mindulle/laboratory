Package bits
============

-   `import "math/bits"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package bits implements bit counting and manipulation functions for the
predeclared unsigned integer types.

Functions in this package may be implemented directly by the compiler,
for better performance. For those functions the code in this package
will not be used. Which functions are implemented by the compiler
depends on the architecture and the Go release.

Index 
-----

-   [Constants](#pkg-constants)
-   [func Add(x, y, carry uint) (sum, carryOut uint)](#Add)
-   [func Add32(x, y, carry uint32) (sum, carryOut uint32)](#Add32)
-   [func Add64(x, y, carry uint64) (sum, carryOut uint64)](#Add64)
-   [func Div(hi, lo, y uint) (quo, rem uint)](#Div)
-   [func Div32(hi, lo, y uint32) (quo, rem uint32)](#Div32)
-   [func Div64(hi, lo, y uint64) (quo, rem uint64)](#Div64)
-   [func LeadingZeros(x uint) int](#LeadingZeros)
-   [func LeadingZeros16(x uint16) int](#LeadingZeros16)
-   [func LeadingZeros32(x uint32) int](#LeadingZeros32)
-   [func LeadingZeros64(x uint64) int](#LeadingZeros64)
-   [func LeadingZeros8(x uint8) int](#LeadingZeros8)
-   [func Len(x uint) int](#Len)
-   [func Len16(x uint16) (n int)](#Len16)
-   [func Len32(x uint32) (n int)](#Len32)
-   [func Len64(x uint64) (n int)](#Len64)
-   [func Len8(x uint8) int](#Len8)
-   [func Mul(x, y uint) (hi, lo uint)](#Mul)
-   [func Mul32(x, y uint32) (hi, lo uint32)](#Mul32)
-   [func Mul64(x, y uint64) (hi, lo uint64)](#Mul64)
-   [func OnesCount(x uint) int](#OnesCount)
-   [func OnesCount16(x uint16) int](#OnesCount16)
-   [func OnesCount32(x uint32) int](#OnesCount32)
-   [func OnesCount64(x uint64) int](#OnesCount64)
-   [func OnesCount8(x uint8) int](#OnesCount8)
-   [func Rem(hi, lo, y uint) uint](#Rem)
-   [func Rem32(hi, lo, y uint32) uint32](#Rem32)
-   [func Rem64(hi, lo, y uint64) uint64](#Rem64)
-   [func Reverse(x uint) uint](#Reverse)
-   [func Reverse16(x uint16) uint16](#Reverse16)
-   [func Reverse32(x uint32) uint32](#Reverse32)
-   [func Reverse64(x uint64) uint64](#Reverse64)
-   [func Reverse8(x uint8) uint8](#Reverse8)
-   [func ReverseBytes(x uint) uint](#ReverseBytes)
-   [func ReverseBytes16(x uint16) uint16](#ReverseBytes16)
-   [func ReverseBytes32(x uint32) uint32](#ReverseBytes32)
-   [func ReverseBytes64(x uint64) uint64](#ReverseBytes64)
-   [func RotateLeft(x uint, k int) uint](#RotateLeft)
-   [func RotateLeft16(x uint16, k int) uint16](#RotateLeft16)
-   [func RotateLeft32(x uint32, k int) uint32](#RotateLeft32)
-   [func RotateLeft64(x uint64, k int) uint64](#RotateLeft64)
-   [func RotateLeft8(x uint8, k int) uint8](#RotateLeft8)
-   [func Sub(x, y, borrow uint) (diff, borrowOut uint)](#Sub)
-   [func Sub32(x, y, borrow uint32) (diff, borrowOut uint32)](#Sub32)
-   [func Sub64(x, y, borrow uint64) (diff, borrowOut uint64)](#Sub64)
-   [func TrailingZeros(x uint) int](#TrailingZeros)
-   [func TrailingZeros16(x uint16) int](#TrailingZeros16)
-   [func TrailingZeros32(x uint32) int](#TrailingZeros32)
-   [func TrailingZeros64(x uint64) int](#TrailingZeros64)
-   [func TrailingZeros8(x uint8) int](#TrailingZeros8)

 
### Examples

[Add32](#example_Add32)

[Add64](#example_Add64)

[Div32](#example_Div32)

[Div64](#example_Div64)

[LeadingZeros16](#example_LeadingZeros16)

[LeadingZeros32](#example_LeadingZeros32)

[LeadingZeros64](#example_LeadingZeros64)

[LeadingZeros8](#example_LeadingZeros8)

[Len16](#example_Len16)

[Len32](#example_Len32)

[Len64](#example_Len64)

[Len8](#example_Len8)

[Mul32](#example_Mul32)

[Mul64](#example_Mul64)

[OnesCount](#example_OnesCount)

[OnesCount16](#example_OnesCount16)

[OnesCount32](#example_OnesCount32)

[OnesCount64](#example_OnesCount64)

[OnesCount8](#example_OnesCount8)

[Reverse16](#example_Reverse16)

[Reverse32](#example_Reverse32)

[Reverse64](#example_Reverse64)

[Reverse8](#example_Reverse8)

[ReverseBytes16](#example_ReverseBytes16)

[ReverseBytes32](#example_ReverseBytes32)

[ReverseBytes64](#example_ReverseBytes64)

[RotateLeft16](#example_RotateLeft16)

[RotateLeft32](#example_RotateLeft32)

[RotateLeft64](#example_RotateLeft64)

[RotateLeft8](#example_RotateLeft8)

[Sub32](#example_Sub32)

[Sub64](#example_Sub64)

[TrailingZeros16](#example_TrailingZeros16)

[TrailingZeros32](#example_TrailingZeros32)

[TrailingZeros64](#example_TrailingZeros64)

[TrailingZeros8](#example_TrailingZeros8)


### Package files

bits.go bits\_errors.go bits\_tables.go

Constants 
---------

UintSize is the size of a uint in bits.

```go
const UintSize = uintSize
```

func Add 
-----------------------------------------

```go
func Add(x, y, carry uint) (sum, carryOut uint)
```

Add returns the sum with carry of x, y and carry: sum = x + y + carry.
The carry input must be 0 or 1; otherwise the behavior is undefined. The
carryOut output is guaranteed to be 0 or 1.

This function\'s execution time does not depend on the inputs.

func Add32 
-------------------------------------------

```go
func Add32(x, y, carry uint32) (sum, carryOut uint32)
```

Add32 returns the sum with carry of x, y and carry: sum = x + y + carry.
The carry input must be 0 or 1; otherwise the behavior is undefined. The
carryOut output is guaranteed to be 0 or 1.

This function\'s execution time does not depend on the inputs.

#### [Example]

Code:

```go
// First number is 33<<32 + 12
n1 := []uint32{33, 12}
// Second number is 21<<32 + 23
n2 := []uint32{21, 23}
// Add them together without producing carry.
d1, carry := bits.Add32(n1[1], n2[1], 0)
d0, _ := bits.Add32(n1[0], n2[0], carry)
nsum := []uint32{d0, d1}
fmt.Printf("%v + %v = %v (carry bit was %v)\n", n1, n2, nsum, carry)

// First number is 1<<32 + 2147483648
n1 = []uint32{1, 0x80000000}
// Second number is 1<<32 + 2147483648
n2 = []uint32{1, 0x80000000}
// Add them together producing carry.
d1, carry = bits.Add32(n1[1], n2[1], 0)
d0, _ = bits.Add32(n1[0], n2[0], carry)
nsum = []uint32{d0, d1}
fmt.Printf("%v + %v = %v (carry bit was %v)\n", n1, n2, nsum, carry)
```

Output:

```go
[33 12] + [21 23] = [54 35] (carry bit was 0)
[1 2147483648] + [1 2147483648] = [3 0] (carry bit was 1)
```

func Add64 
-------------------------------------------

```go
func Add64(x, y, carry uint64) (sum, carryOut uint64)
```

Add64 returns the sum with carry of x, y and carry: sum = x + y + carry.
The carry input must be 0 or 1; otherwise the behavior is undefined. The
carryOut output is guaranteed to be 0 or 1.

This function\'s execution time does not depend on the inputs.

#### [Example]

Code:

```go
// First number is 33<<64 + 12
n1 := []uint64{33, 12}
// Second number is 21<<64 + 23
n2 := []uint64{21, 23}
// Add them together without producing carry.
d1, carry := bits.Add64(n1[1], n2[1], 0)
d0, _ := bits.Add64(n1[0], n2[0], carry)
nsum := []uint64{d0, d1}
fmt.Printf("%v + %v = %v (carry bit was %v)\n", n1, n2, nsum, carry)

// First number is 1<<64 + 9223372036854775808
n1 = []uint64{1, 0x8000000000000000}
// Second number is 1<<64 + 9223372036854775808
n2 = []uint64{1, 0x8000000000000000}
// Add them together producing carry.
d1, carry = bits.Add64(n1[1], n2[1], 0)
d0, _ = bits.Add64(n1[0], n2[0], carry)
nsum = []uint64{d0, d1}
fmt.Printf("%v + %v = %v (carry bit was %v)\n", n1, n2, nsum, carry)
```

Output:

```go
[33 12] + [21 23] = [54 35] (carry bit was 0)
[1 9223372036854775808] + [1 9223372036854775808] = [3 0] (carry bit was 1)
```

func Div 
-----------------------------------------

```go
func Div(hi, lo, y uint) (quo, rem uint)
```

Div returns the quotient and remainder of (hi, lo) divided by y: quo =
(hi, lo)/y, rem = (hi, lo)%y with the dividend bits\' upper half in
parameter hi and the lower half in parameter lo. Div panics for y == 0
(division by zero) or y \<= hi (quotient overflow).

func Div32 
-------------------------------------------

```go
func Div32(hi, lo, y uint32) (quo, rem uint32)
```

Div32 returns the quotient and remainder of (hi, lo) divided by y: quo =
(hi, lo)/y, rem = (hi, lo)%y with the dividend bits\' upper half in
parameter hi and the lower half in parameter lo. Div32 panics for y == 0
(division by zero) or y \<= hi (quotient overflow).

#### [Example]

Code:

```go
// First number is 0<<32 + 6
n1 := []uint32{0, 6}
// Second number is 0<<32 + 3
n2 := []uint32{0, 3}
// Divide them together.
quo, rem := bits.Div32(n1[0], n1[1], n2[1])
nsum := []uint32{quo, rem}
fmt.Printf("[%v %v] / %v = %v\n", n1[0], n1[1], n2[1], nsum)

// First number is 2<<32 + 2147483648
n1 = []uint32{2, 0x80000000}
// Second number is 0<<32 + 2147483648
n2 = []uint32{0, 0x80000000}
// Divide them together.
quo, rem = bits.Div32(n1[0], n1[1], n2[1])
nsum = []uint32{quo, rem}
fmt.Printf("[%v %v] / %v = %v\n", n1[0], n1[1], n2[1], nsum)
```

Output:

```go
[0 6] / 3 = [2 0]
[2 2147483648] / 2147483648 = [5 0]
```

func Div64 
-------------------------------------------

```go
func Div64(hi, lo, y uint64) (quo, rem uint64)
```

Div64 returns the quotient and remainder of (hi, lo) divided by y: quo =
(hi, lo)/y, rem = (hi, lo)%y with the dividend bits\' upper half in
parameter hi and the lower half in parameter lo. Div64 panics for y == 0
(division by zero) or y \<= hi (quotient overflow).

#### [Example]

Code:

```go
// First number is 0<<64 + 6
n1 := []uint64{0, 6}
// Second number is 0<<64 + 3
n2 := []uint64{0, 3}
// Divide them together.
quo, rem := bits.Div64(n1[0], n1[1], n2[1])
nsum := []uint64{quo, rem}
fmt.Printf("[%v %v] / %v = %v\n", n1[0], n1[1], n2[1], nsum)

// First number is 2<<64 + 9223372036854775808
n1 = []uint64{2, 0x8000000000000000}
// Second number is 0<<64 + 9223372036854775808
n2 = []uint64{0, 0x8000000000000000}
// Divide them together.
quo, rem = bits.Div64(n1[0], n1[1], n2[1])
nsum = []uint64{quo, rem}
fmt.Printf("[%v %v] / %v = %v\n", n1[0], n1[1], n2[1], nsum)
```

Output:

```go
[0 6] / 3 = [2 0]
[2 9223372036854775808] / 9223372036854775808 = [5 0]
```

func LeadingZeros 
------------------------------------------------

```go
func LeadingZeros(x uint) int
```

LeadingZeros returns the number of leading zero bits in x; the result is
UintSize for x == 0.

func LeadingZeros16 
--------------------------------------------------

```go
func LeadingZeros16(x uint16) int
```

LeadingZeros16 returns the number of leading zero bits in x; the result
is 16 for x == 0.

#### [Example]

Code:

```go
fmt.Printf("LeadingZeros16(%016b) = %d\n", 1, bits.LeadingZeros16(1))
```

Output:

```go
LeadingZeros16(0000000000000001) = 15
```

func LeadingZeros32 
--------------------------------------------------

```go
func LeadingZeros32(x uint32) int
```

LeadingZeros32 returns the number of leading zero bits in x; the result
is 32 for x == 0.

#### [Example]

Code:

```go
fmt.Printf("LeadingZeros32(%032b) = %d\n", 1, bits.LeadingZeros32(1))
```

Output:

```go
LeadingZeros32(00000000000000000000000000000001) = 31
```

func LeadingZeros64 
--------------------------------------------------

```go
func LeadingZeros64(x uint64) int
```

LeadingZeros64 returns the number of leading zero bits in x; the result
is 64 for x == 0.

#### [Example]

Code:

```go
fmt.Printf("LeadingZeros64(%064b) = %d\n", 1, bits.LeadingZeros64(1))
```

Output:

```go
LeadingZeros64(0000000000000000000000000000000000000000000000000000000000000001) = 63
```

func LeadingZeros8 
-------------------------------------------------

```go
func LeadingZeros8(x uint8) int
```

LeadingZeros8 returns the number of leading zero bits in x; the result
is 8 for x == 0.

#### [Example]

Code:

```go
fmt.Printf("LeadingZeros8(%08b) = %d\n", 1, bits.LeadingZeros8(1))
```

Output:

```go
LeadingZeros8(00000001) = 7
```

func Len 
---------------------------------------

```go
func Len(x uint) int
```

Len returns the minimum number of bits required to represent x; the
result is 0 for x == 0.

func Len16 
-----------------------------------------

```go
func Len16(x uint16) (n int)
```

Len16 returns the minimum number of bits required to represent x; the
result is 0 for x == 0.

#### [Example]

Code:

```go
fmt.Printf("Len16(%016b) = %d\n", 8, bits.Len16(8))
```

Output:

```go
Len16(0000000000001000) = 4
```

func Len32 
-----------------------------------------

```go
func Len32(x uint32) (n int)
```

Len32 returns the minimum number of bits required to represent x; the
result is 0 for x == 0.

#### [Example]

Code:

```go
fmt.Printf("Len32(%032b) = %d\n", 8, bits.Len32(8))
```

Output:

```go
Len32(00000000000000000000000000001000) = 4
```

func Len64 
-----------------------------------------

```go
func Len64(x uint64) (n int)
```

Len64 returns the minimum number of bits required to represent x; the
result is 0 for x == 0.

#### [Example]

Code:

```go
fmt.Printf("Len64(%064b) = %d\n", 8, bits.Len64(8))
```

Output:

```go
Len64(0000000000000000000000000000000000000000000000000000000000001000) = 4
```

func Len8 
----------------------------------------

```go
func Len8(x uint8) int
```

Len8 returns the minimum number of bits required to represent x; the
result is 0 for x == 0.

#### [Example]

Code:

```go
fmt.Printf("Len8(%08b) = %d\n", 8, bits.Len8(8))
```

Output:

```go
Len8(00001000) = 4
```

func Mul 
-----------------------------------------

```go
func Mul(x, y uint) (hi, lo uint)
```

Mul returns the full-width product of x and y: (hi, lo) = x \* y with
the product bits\' upper half returned in hi and the lower half returned
in lo.

This function\'s execution time does not depend on the inputs.

func Mul32 
-------------------------------------------

```go
func Mul32(x, y uint32) (hi, lo uint32)
```

Mul32 returns the 64-bit product of x and y: (hi, lo) = x \* y with the
product bits\' upper half returned in hi and the lower half returned in
lo.

This function\'s execution time does not depend on the inputs.

#### [Example]

Code:

```go
// First number is 0<<32 + 12
n1 := []uint32{0, 12}
// Second number is 0<<32 + 12
n2 := []uint32{0, 12}
// Multiply them together without producing overflow.
hi, lo := bits.Mul32(n1[1], n2[1])
nsum := []uint32{hi, lo}
fmt.Printf("%v * %v = %v\n", n1[1], n2[1], nsum)

// First number is 0<<32 + 2147483648
n1 = []uint32{0, 0x80000000}
// Second number is 0<<32 + 2
n2 = []uint32{0, 2}
// Multiply them together producing overflow.
hi, lo = bits.Mul32(n1[1], n2[1])
nsum = []uint32{hi, lo}
fmt.Printf("%v * %v = %v\n", n1[1], n2[1], nsum)
```

Output:

```go
12 * 12 = [0 144]
2147483648 * 2 = [1 0]
```

func Mul64 
-------------------------------------------

```go
func Mul64(x, y uint64) (hi, lo uint64)
```

Mul64 returns the 128-bit product of x and y: (hi, lo) = x \* y with the
product bits\' upper half returned in hi and the lower half returned in
lo.

This function\'s execution time does not depend on the inputs.

#### [Example]

Code:

```go
// First number is 0<<64 + 12
n1 := []uint64{0, 12}
// Second number is 0<<64 + 12
n2 := []uint64{0, 12}
// Multiply them together without producing overflow.
hi, lo := bits.Mul64(n1[1], n2[1])
nsum := []uint64{hi, lo}
fmt.Printf("%v * %v = %v\n", n1[1], n2[1], nsum)

// First number is 0<<64 + 9223372036854775808
n1 = []uint64{0, 0x8000000000000000}
// Second number is 0<<64 + 2
n2 = []uint64{0, 2}
// Multiply them together producing overflow.
hi, lo = bits.Mul64(n1[1], n2[1])
nsum = []uint64{hi, lo}
fmt.Printf("%v * %v = %v\n", n1[1], n2[1], nsum)
```

Output:

```go
12 * 12 = [0 144]
9223372036854775808 * 2 = [1 0]
```

func OnesCount 
---------------------------------------------

```go
func OnesCount(x uint) int
```

OnesCount returns the number of one bits (\"population count\") in x.

#### [Example]

Code:

```go
fmt.Printf("OnesCount(%b) = %d\n", 14, bits.OnesCount(14))
```

Output:

```go
OnesCount(1110) = 3
```

func OnesCount16 
-----------------------------------------------

```go
func OnesCount16(x uint16) int
```

OnesCount16 returns the number of one bits (\"population count\") in x.

#### [Example]

Code:

```go
fmt.Printf("OnesCount16(%016b) = %d\n", 14, bits.OnesCount16(14))
```

Output:

```go
OnesCount16(0000000000001110) = 3
```

func OnesCount32 
-----------------------------------------------

```go
func OnesCount32(x uint32) int
```

OnesCount32 returns the number of one bits (\"population count\") in x.

#### [Example]

Code:

```go
fmt.Printf("OnesCount32(%032b) = %d\n", 14, bits.OnesCount32(14))
```

Output:

```go
OnesCount32(00000000000000000000000000001110) = 3
```

func OnesCount64 
-----------------------------------------------

```go
func OnesCount64(x uint64) int
```

OnesCount64 returns the number of one bits (\"population count\") in x.

#### [Example]

Code:

```go
fmt.Printf("OnesCount64(%064b) = %d\n", 14, bits.OnesCount64(14))
```

Output:

```go
OnesCount64(0000000000000000000000000000000000000000000000000000000000001110) = 3
```

func OnesCount8 
----------------------------------------------

```go
func OnesCount8(x uint8) int
```

OnesCount8 returns the number of one bits (\"population count\") in x.

#### [Example]

Code:

```go
fmt.Printf("OnesCount8(%08b) = %d\n", 14, bits.OnesCount8(14))
```

Output:

```go
OnesCount8(00001110) = 3
```

func Rem 
-----------------------------------------

```go
func Rem(hi, lo, y uint) uint
```

Rem returns the remainder of (hi, lo) divided by y. Rem panics for y ==
0 (division by zero) but, unlike Div, it doesn\'t panic on a quotient
overflow.

func Rem32 
-------------------------------------------

```go
func Rem32(hi, lo, y uint32) uint32
```

Rem32 returns the remainder of (hi, lo) divided by y. Rem32 panics for y
== 0 (division by zero) but, unlike Div32, it doesn\'t panic on a
quotient overflow.

func Rem64 
-------------------------------------------

```go
func Rem64(hi, lo, y uint64) uint64
```

Rem64 returns the remainder of (hi, lo) divided by y. Rem64 panics for y
== 0 (division by zero) but, unlike Div64, it doesn\'t panic on a
quotient overflow.

func Reverse 
-------------------------------------------

```go
func Reverse(x uint) uint
```

Reverse returns the value of x with its bits in reversed order.

func Reverse16 
---------------------------------------------

```go
func Reverse16(x uint16) uint16
```

Reverse16 returns the value of x with its bits in reversed order.

#### [Example]

Code:

```go
fmt.Printf("%016b\n", 19)
fmt.Printf("%016b\n", bits.Reverse16(19))
```

Output:

```go
0000000000010011
1100100000000000
```

func Reverse32 
---------------------------------------------

```go
func Reverse32(x uint32) uint32
```

Reverse32 returns the value of x with its bits in reversed order.

#### [Example]

Code:

```go
fmt.Printf("%032b\n", 19)
fmt.Printf("%032b\n", bits.Reverse32(19))
```

Output:

```go
00000000000000000000000000010011
11001000000000000000000000000000
```

func Reverse64 
---------------------------------------------

```go
func Reverse64(x uint64) uint64
```

Reverse64 returns the value of x with its bits in reversed order.

#### [Example]

Code:

```go
fmt.Printf("%064b\n", 19)
fmt.Printf("%064b\n", bits.Reverse64(19))
```

Output:

```go
0000000000000000000000000000000000000000000000000000000000010011
1100100000000000000000000000000000000000000000000000000000000000
```

func Reverse8 
--------------------------------------------

```go
func Reverse8(x uint8) uint8
```

Reverse8 returns the value of x with its bits in reversed order.

#### [Example]

Code:

```go
fmt.Printf("%08b\n", 19)
fmt.Printf("%08b\n", bits.Reverse8(19))
```

Output:

```go
00010011
11001000
```

func ReverseBytes 
------------------------------------------------

```go
func ReverseBytes(x uint) uint
```

ReverseBytes returns the value of x with its bytes in reversed order.

This function\'s execution time does not depend on the inputs.

func ReverseBytes16 
--------------------------------------------------

```go
func ReverseBytes16(x uint16) uint16
```

ReverseBytes16 returns the value of x with its bytes in reversed order.

This function\'s execution time does not depend on the inputs.

#### [Example]

Code:

```go
fmt.Printf("%016b\n", 15)
fmt.Printf("%016b\n", bits.ReverseBytes16(15))
```

Output:

```go
0000000000001111
0000111100000000
```

func ReverseBytes32 
--------------------------------------------------

```go
func ReverseBytes32(x uint32) uint32
```

ReverseBytes32 returns the value of x with its bytes in reversed order.

This function\'s execution time does not depend on the inputs.

#### [Example]

Code:

```go
fmt.Printf("%032b\n", 15)
fmt.Printf("%032b\n", bits.ReverseBytes32(15))
```

Output:

```go
00000000000000000000000000001111
00001111000000000000000000000000
```

func ReverseBytes64 
--------------------------------------------------

```go
func ReverseBytes64(x uint64) uint64
```

ReverseBytes64 returns the value of x with its bytes in reversed order.

This function\'s execution time does not depend on the inputs.

#### [Example]

Code:

```go
fmt.Printf("%064b\n", 15)
fmt.Printf("%064b\n", bits.ReverseBytes64(15))
```

Output:

```go
0000000000000000000000000000000000000000000000000000000000001111
0000111100000000000000000000000000000000000000000000000000000000
```

func RotateLeft 
----------------------------------------------

```go
func RotateLeft(x uint, k int) uint
```

RotateLeft returns the value of x rotated left by (k mod UintSize) bits.
To rotate x right by k bits, call RotateLeft(x, -k).

This function\'s execution time does not depend on the inputs.

func RotateLeft16 
------------------------------------------------

```go
func RotateLeft16(x uint16, k int) uint16
```

RotateLeft16 returns the value of x rotated left by (k mod 16) bits. To
rotate x right by k bits, call RotateLeft16(x, -k).

This function\'s execution time does not depend on the inputs.

#### [Example]

Code:

```go
fmt.Printf("%016b\n", 15)
fmt.Printf("%016b\n", bits.RotateLeft16(15, 2))
fmt.Printf("%016b\n", bits.RotateLeft16(15, -2))
```

Output:

```go
0000000000001111
0000000000111100
1100000000000011
```

func RotateLeft32 
------------------------------------------------

```go
func RotateLeft32(x uint32, k int) uint32
```

RotateLeft32 returns the value of x rotated left by (k mod 32) bits. To
rotate x right by k bits, call RotateLeft32(x, -k).

This function\'s execution time does not depend on the inputs.

#### [Example]

Code:

```go
fmt.Printf("%032b\n", 15)
fmt.Printf("%032b\n", bits.RotateLeft32(15, 2))
fmt.Printf("%032b\n", bits.RotateLeft32(15, -2))
```

Output:

```go
00000000000000000000000000001111
00000000000000000000000000111100
11000000000000000000000000000011
```

func RotateLeft64 
------------------------------------------------

```go
func RotateLeft64(x uint64, k int) uint64
```

RotateLeft64 returns the value of x rotated left by (k mod 64) bits. To
rotate x right by k bits, call RotateLeft64(x, -k).

This function\'s execution time does not depend on the inputs.

#### [Example]

Code:

```go
fmt.Printf("%064b\n", 15)
fmt.Printf("%064b\n", bits.RotateLeft64(15, 2))
fmt.Printf("%064b\n", bits.RotateLeft64(15, -2))
```

Output:

```go
0000000000000000000000000000000000000000000000000000000000001111
0000000000000000000000000000000000000000000000000000000000111100
1100000000000000000000000000000000000000000000000000000000000011
```

func RotateLeft8 
-----------------------------------------------

```go
func RotateLeft8(x uint8, k int) uint8
```

RotateLeft8 returns the value of x rotated left by (k mod 8) bits. To
rotate x right by k bits, call RotateLeft8(x, -k).

This function\'s execution time does not depend on the inputs.

#### [Example]

Code:

```go
fmt.Printf("%08b\n", 15)
fmt.Printf("%08b\n", bits.RotateLeft8(15, 2))
fmt.Printf("%08b\n", bits.RotateLeft8(15, -2))
```

Output:

```go
00001111
00111100
11000011
```

func Sub 
-----------------------------------------

```go
func Sub(x, y, borrow uint) (diff, borrowOut uint)
```

Sub returns the difference of x, y and borrow: diff = x - y - borrow.
The borrow input must be 0 or 1; otherwise the behavior is undefined.
The borrowOut output is guaranteed to be 0 or 1.

This function\'s execution time does not depend on the inputs.

func Sub32 
-------------------------------------------

```go
func Sub32(x, y, borrow uint32) (diff, borrowOut uint32)
```

Sub32 returns the difference of x, y and borrow, diff = x - y - borrow.
The borrow input must be 0 or 1; otherwise the behavior is undefined.
The borrowOut output is guaranteed to be 0 or 1.

This function\'s execution time does not depend on the inputs.

#### [Example]

Code:

```go
// First number is 33<<32 + 23
n1 := []uint32{33, 23}
// Second number is 21<<32 + 12
n2 := []uint32{21, 12}
// Sub them together without producing carry.
d1, carry := bits.Sub32(n1[1], n2[1], 0)
d0, _ := bits.Sub32(n1[0], n2[0], carry)
nsum := []uint32{d0, d1}
fmt.Printf("%v - %v = %v (carry bit was %v)\n", n1, n2, nsum, carry)

// First number is 3<<32 + 2147483647
n1 = []uint32{3, 0x7fffffff}
// Second number is 1<<32 + 2147483648
n2 = []uint32{1, 0x80000000}
// Sub them together producing carry.
d1, carry = bits.Sub32(n1[1], n2[1], 0)
d0, _ = bits.Sub32(n1[0], n2[0], carry)
nsum = []uint32{d0, d1}
fmt.Printf("%v - %v = %v (carry bit was %v)\n", n1, n2, nsum, carry)
```

Output:

```go
[33 23] - [21 12] = [12 11] (carry bit was 0)
[3 2147483647] - [1 2147483648] = [1 4294967295] (carry bit was 1)
```

func Sub64 
-------------------------------------------

```go
func Sub64(x, y, borrow uint64) (diff, borrowOut uint64)
```

Sub64 returns the difference of x, y and borrow: diff = x - y - borrow.
The borrow input must be 0 or 1; otherwise the behavior is undefined.
The borrowOut output is guaranteed to be 0 or 1.

This function\'s execution time does not depend on the inputs.

#### [Example]

Code:

```go
// First number is 33<<64 + 23
n1 := []uint64{33, 23}
// Second number is 21<<64 + 12
n2 := []uint64{21, 12}
// Sub them together without producing carry.
d1, carry := bits.Sub64(n1[1], n2[1], 0)
d0, _ := bits.Sub64(n1[0], n2[0], carry)
nsum := []uint64{d0, d1}
fmt.Printf("%v - %v = %v (carry bit was %v)\n", n1, n2, nsum, carry)

// First number is 3<<64 + 9223372036854775807
n1 = []uint64{3, 0x7fffffffffffffff}
// Second number is 1<<64 + 9223372036854775808
n2 = []uint64{1, 0x8000000000000000}
// Sub them together producing carry.
d1, carry = bits.Sub64(n1[1], n2[1], 0)
d0, _ = bits.Sub64(n1[0], n2[0], carry)
nsum = []uint64{d0, d1}
fmt.Printf("%v - %v = %v (carry bit was %v)\n", n1, n2, nsum, carry)
```

Output:

```go
[33 23] - [21 12] = [12 11] (carry bit was 0)
[3 9223372036854775807] - [1 9223372036854775808] = [1 18446744073709551615] (carry bit was 1)
```

func TrailingZeros 
-------------------------------------------------

```go
func TrailingZeros(x uint) int
```

TrailingZeros returns the number of trailing zero bits in x; the result
is UintSize for x == 0.

func TrailingZeros16 
---------------------------------------------------

```go
func TrailingZeros16(x uint16) int
```

TrailingZeros16 returns the number of trailing zero bits in x; the
result is 16 for x == 0.

#### [Example]

Code:

```go
fmt.Printf("TrailingZeros16(%016b) = %d\n", 14, bits.TrailingZeros16(14))
```

Output:

```go
TrailingZeros16(0000000000001110) = 1
```

func TrailingZeros32 
---------------------------------------------------

```go
func TrailingZeros32(x uint32) int
```

TrailingZeros32 returns the number of trailing zero bits in x; the
result is 32 for x == 0.

#### [Example]

Code:

```go
fmt.Printf("TrailingZeros32(%032b) = %d\n", 14, bits.TrailingZeros32(14))
```

Output:

```go
TrailingZeros32(00000000000000000000000000001110) = 1
```

func TrailingZeros64 
---------------------------------------------------

```go
func TrailingZeros64(x uint64) int
```

TrailingZeros64 returns the number of trailing zero bits in x; the
result is 64 for x == 0.

#### [Example]

Code:

```go
fmt.Printf("TrailingZeros64(%064b) = %d\n", 14, bits.TrailingZeros64(14))
```

Output:

```go
TrailingZeros64(0000000000000000000000000000000000000000000000000000000000001110) = 1
```

func TrailingZeros8 
--------------------------------------------------

```go
func TrailingZeros8(x uint8) int
```

TrailingZeros8 returns the number of trailing zero bits in x; the result
is 8 for x == 0.

#### [Example]

Code:

```go
fmt.Printf("TrailingZeros8(%08b) = %d\n", 14, bits.TrailingZeros8(14))
```

Output:

```go
TrailingZeros8(00001110) = 1
```

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/math/bits/>

