Package cmplx
=============

-   `import "math/cmplx"`
-   [Overview](#pkg-overview)
-   [Index](#pkg-index)
-   [Examples](#pkg-examples)

Overview 
--------

Package cmplx provides basic constants and mathematical functions for
complex numbers. Special case handling conforms to the C99 standard
Annex G IEC 60559-compatible complex arithmetic.

Index 
-----

-   [func Abs(x complex128) float64](#Abs)
-   [func Acos(x complex128) complex128](#Acos)
-   [func Acosh(x complex128) complex128](#Acosh)
-   [func Asin(x complex128) complex128](#Asin)
-   [func Asinh(x complex128) complex128](#Asinh)
-   [func Atan(x complex128) complex128](#Atan)
-   [func Atanh(x complex128) complex128](#Atanh)
-   [func Conj(x complex128) complex128](#Conj)
-   [func Cos(x complex128) complex128](#Cos)
-   [func Cosh(x complex128) complex128](#Cosh)
-   [func Cot(x complex128) complex128](#Cot)
-   [func Exp(x complex128) complex128](#Exp)
-   [func Inf() complex128](#Inf)
-   [func IsInf(x complex128) bool](#IsInf)
-   [func IsNaN(x complex128) bool](#IsNaN)
-   [func Log(x complex128) complex128](#Log)
-   [func Log10(x complex128) complex128](#Log10)
-   [func NaN() complex128](#NaN)
-   [func Phase(x complex128) float64](#Phase)
-   [func Polar(x complex128) (r, θ float64)](#Polar)
-   [func Pow(x, y complex128) complex128](#Pow)
-   [func Rect(r, θ float64) complex128](#Rect)
-   [func Sin(x complex128) complex128](#Sin)
-   [func Sinh(x complex128) complex128](#Sinh)
-   [func Sqrt(x complex128) complex128](#Sqrt)
-   [func Tan(x complex128) complex128](#Tan)
-   [func Tanh(x complex128) complex128](#Tanh)

 
### Examples

[Abs](#example_Abs)

[Exp](#example_Exp)

[Polar](#example_Polar)


### Package files

abs.go asin.go conj.go exp.go isinf.go isnan.go log.go phase.go polar.go
pow.go rect.go sin.go sqrt.go tan.go

func Abs 
--------

```go
func Abs(x complex128) float64
```

Abs returns the absolute value (also called the modulus) of x.

#### [Example]

Code:

```go
fmt.Printf("%.1f", cmplx.Abs(3+4i))
```

Output:

```go
5.0
```

func Acos 
---------

```go
func Acos(x complex128) complex128
```

Acos returns the inverse cosine of x.

func Acosh 
----------

```go
func Acosh(x complex128) complex128
```

Acosh returns the inverse hyperbolic cosine of x.

func Asin 
---------

```go
func Asin(x complex128) complex128
```

Asin returns the inverse sine of x.

func Asinh 
----------

```go
func Asinh(x complex128) complex128
```

Asinh returns the inverse hyperbolic sine of x.

func Atan 
---------

```go
func Atan(x complex128) complex128
```

Atan returns the inverse tangent of x.

func Atanh 
----------

```go
func Atanh(x complex128) complex128
```

Atanh returns the inverse hyperbolic tangent of x.

func Conj 
---------

```go
func Conj(x complex128) complex128
```

Conj returns the complex conjugate of x.

func Cos 
--------

```go
func Cos(x complex128) complex128
```

Cos returns the cosine of x.

func Cosh 
---------

```go
func Cosh(x complex128) complex128
```

Cosh returns the hyperbolic cosine of x.

func Cot 
--------

```go
func Cot(x complex128) complex128
```

Cot returns the cotangent of x.

func Exp 
--------

```go
func Exp(x complex128) complex128
```

Exp returns e\*\*x, the base-e exponential of x.

#### [Example]

ExampleExp computes Euler\'s identity.

Code:

```go
fmt.Printf("%.1f", cmplx.Exp(1i*math.Pi)+1)
```

Output:

```go
(0.0+0.0i)
```

func Inf 
--------

```go
func Inf() complex128
```

Inf returns a complex infinity, complex(+Inf, +Inf).

func IsInf 
----------

```go
func IsInf(x complex128) bool
```

IsInf reports whether either real(x) or imag(x) is an infinity.

func IsNaN 
----------

```go
func IsNaN(x complex128) bool
```

IsNaN reports whether either real(x) or imag(x) is NaN and neither is an
infinity.

func Log 
--------

```go
func Log(x complex128) complex128
```

Log returns the natural logarithm of x.

func Log10 
----------

```go
func Log10(x complex128) complex128
```

Log10 returns the decimal logarithm of x.

func NaN 
--------

```go
func NaN() complex128
```

NaN returns a complex "not-a-number" value.

func Phase 
----------

```go
func Phase(x complex128) float64
```

Phase returns the phase (also called the argument) of x. The returned
value is in the range \[-Pi, Pi\].

func Polar 
----------

```go
func Polar(x complex128) (r, θ float64)
```

Polar returns the absolute value r and phase θ of x, such that x = r \*
e\*\*θi. The phase is in the range \[-Pi, Pi\].

#### [Example]

Code:

```go
r, theta := cmplx.Polar(2i)
fmt.Printf("r: %.1f, θ: %.1f*π", r, theta/math.Pi)
```

Output:

```go
r: 2.0, θ: 0.5*π
```

func Pow 
--------

```go
func Pow(x, y complex128) complex128
```

Pow returns x\*\*y, the base-x exponential of y. For generalized
compatibility with math.Pow:

```go
Pow(0, ±0) returns 1+0i
Pow(0, c) for real(c)<0 returns Inf+0i if imag(c) is zero, otherwise Inf+Inf i.
```

func Rect 
---------

```go
func Rect(r, θ float64) complex128
```

Rect returns the complex number x with polar coordinates r, θ.

func Sin 
--------

```go
func Sin(x complex128) complex128
```

Sin returns the sine of x.

func Sinh 
---------

```go
func Sinh(x complex128) complex128
```

Sinh returns the hyperbolic sine of x.

func Sqrt 
---------

```go
func Sqrt(x complex128) complex128
```

Sqrt returns the square root of x. The result r is chosen so that
real(r) ≥ 0 and imag(r) has the same sign as imag(x).

func Tan 
--------

```go
func Tan(x complex128) complex128
```

Tan returns the tangent of x.

func Tanh 
---------

```go
func Tanh(x complex128) complex128
```

Tanh returns the hyperbolic tangent of x.

 
© Google, Inc.\
Licensed under the Creative Commons Attribution License 3.0.\
https://golang.org/pkg/math/cmplx/>

