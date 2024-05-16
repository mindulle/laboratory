Math
====

 
The `Math` namespace object contains static properties and methods for
mathematical constants and functions.

`Math` works with the [`Number`](number) type. It doesn\'t work with
[`BigInt`](bigint).


 
Description
-----------

 
Unlike most global objects, `Math` is not a constructor. You cannot use
it with the [`new` operator](../operators/new) or invoke the `Math`
object as a function. All properties and methods of `Math` are static.

 
**Note:** Many `Math` functions have a precision that\'s
*implementation-dependent*.

This means that different browsers can give a different result. Even the
same JavaScript engine on a different OS or architecture can give
different results!




 
Static properties 
-----------------

 

[`Math.E`](math/e)

:   Euler\'s number and the base of natural logarithms; approximately
    `2.718`.

[`Math.LN10`](math/ln10)

:   Natural logarithm of `10`; approximately `2.303`.

[`Math.LN2`](math/ln2)

:   Natural logarithm of `2`; approximately `0.693`.

[`Math.LOG10E`](math/log10e)

:   Base-10 logarithm of `E`; approximately `0.434`.

[`Math.LOG2E`](math/log2e)

:   Base-2 logarithm of `E`; approximately `1.443`.

[`Math.PI`](math/pi)

:   Ratio of a circle\'s circumference to its diameter; approximately
    `3.14159`.

[`Math.SQRT1_2`](math/sqrt1_2)

:   Square root of ½; approximately `0.707`.

[`Math.SQRT2`](math/sqrt2)

:   Square root of `2`; approximately `1.414`.

[`Math[@@toStringTag]`](#mathtostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"Math"`. This property is used in
    [`Object.prototype.toString()`](object/tostring).



 
Static methods 
--------------

 

[`Math.abs()`](math/abs)

:   Returns the absolute value of `x`.

[`Math.acos()`](math/acos)

:   Returns the arccosine of `x`.

[`Math.acosh()`](math/acosh)

:   Returns the hyperbolic arccosine of `x`.

[`Math.asin()`](math/asin)

:   Returns the arcsine of `x`.

[`Math.asinh()`](math/asinh)

:   Returns the hyperbolic arcsine of a number.

[`Math.atan()`](math/atan)

:   Returns the arctangent of `x`.

[`Math.atan2()`](math/atan2)

:   Returns the arctangent of the quotient of its arguments.

[`Math.atanh()`](math/atanh)

:   Returns the hyperbolic arctangent of `x`.

[`Math.cbrt()`](math/cbrt)

:   Returns the cube root of `x`.

[`Math.ceil()`](math/ceil)

:   Returns the smallest integer greater than or equal to `x`.

[`Math.clz32()`](math/clz32)

:   Returns the number of leading zero bits of the 32-bit integer `x`.

[`Math.cos()`](math/cos)

:   Returns the cosine of `x`.

[`Math.cosh()`](math/cosh)

:   Returns the hyperbolic cosine of `x`.

[`Math.exp()`](math/exp)

:   Returns e^x^, where x is the argument, and e is Euler\'s number
    (`2.718`..., the base of the natural logarithm).

[`Math.expm1()`](math/expm1)

:   Returns subtracting `1` from `exp(x)`.

[`Math.floor()`](math/floor)

:   Returns the largest integer less than or equal to `x`.

[`Math.fround()`](math/fround)

:   Returns the nearest [single
    precision](https://en.wikipedia.org/wiki/Single-precision_floating-point_format)
    float representation of `x`.

[`Math.hypot()`](math/hypot)

:   Returns the square root of the sum of squares of its arguments.

[`Math.imul()`](math/imul)

:   Returns the result of the 32-bit integer multiplication of `x` and
    `y`.

[`Math.log()`](math/log)

:   Returns the natural logarithm (㏒~e~; also, ㏑) of `x`.

[`Math.log10()`](math/log10)

:   Returns the base-10 logarithm of `x`.

[`Math.log1p()`](math/log1p)

:   Returns the natural logarithm (㏒~e~; also ㏑) of `1 + x` for the
    number `x`.

[`Math.log2()`](math/log2)

:   Returns the base-2 logarithm of `x`.

[`Math.max()`](math/max)

:   Returns the largest of zero or more numbers.

[`Math.min()`](math/min)

:   Returns the smallest of zero or more numbers.

[`Math.pow()`](math/pow)

:   Returns base `x` to the exponent power `y` (that is, `x`^`y`^).

[`Math.random()`](math/random)

:   Returns a pseudo-random number between `0` and `1`.

[`Math.round()`](math/round)

:   Returns the value of the number `x` rounded to the nearest integer.

[`Math.sign()`](math/sign)

:   Returns the sign of the `x`, indicating whether `x` is positive,
    negative, or zero.

[`Math.sin()`](math/sin)

:   Returns the sine of `x`.

[`Math.sinh()`](math/sinh)

:   Returns the hyperbolic sine of `x`.

[`Math.sqrt()`](math/sqrt)

:   Returns the positive square root of `x`.

[`Math.tan()`](math/tan)

:   Returns the tangent of `x`.

[`Math.tanh()`](math/tanh)

:   Returns the hyperbolic tangent of `x`.

[`Math.trunc()`](math/trunc)

:   Returns the integer portion of `x`, removing any fractional digits.



 
Examples
--------


 
### Converting between degrees and radians 

 
The trigonometric functions `sin()`, `cos()`, `tan()`, `asin()`,
`acos()`, `atan()`, and `atan2()` expect (and return) angles in
*radians*.

Since humans tend to think in degrees, and some functions (such as CSS
transforms) can accept degrees, it is a good idea to keep functions
handy that convert between the two:

 
 
[js]


```js
function degToRad(degrees) {
  return degrees * (Math.PI / 180);
}

function radToDeg(rad) {
  return rad / (Math.PI / 180);
}
```




 
### Calculating the height of an equilateral triangle 

 
If we want to calculate the height of an equilateral triangle, and we
know its side length is 100, we can use the formulae *length of the
adjacent multiplied by the tangent of the angle is equal to the
opposite.*

![An equilateral triangle where a perpendicular of one edge is drawn
from the opposite vertex, forming a right triangle with three sides
marked as \"adjacent\", \"opposite\", and \"hypotenuse\". The angle
between the \"adjacent\" and \"hypotenuse\" sides is 60


In JavaScript, we can do this with the following:

 
 
[js]


```js
50 * Math.tan(degToRad(60));
```


We use our `degToRad()` function to convert 60 degrees to radians, as
[`Math.tan()`](math/tan) expects an input value in radians.



 
### Returning a random integer between two bounds 

 
This can be achieved with a combination of
[`Math.random()`](math/random) and [`Math.floor()`](math/floor):

 
 
[js]


```js
function random(min, max) {
  const num = Math.floor(Math.random() * (max - min + 1)) + min;
  return num;
}

random(1, 10);
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math-object]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math-object)

  -----------------------------------------------------------------------------------------------------


Browser compatibility 
---------------------

 


Desktop

Mobile

Server

Chrome

Edge

Firefox

Opera

Safari

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

WebView Android

Deno

Node.js

`E`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`LN10`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`LN2`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`LOG10E`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`LOG2E`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`PI`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`SQRT1_2`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`SQRT2`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`Math`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`abs`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`acos`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`acosh`

38

12

25

25

8

38

25

25

8

3.0

38

1.0

0.12.0

`asin`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`asinh`

38

12

25

25

8

38

25

25

8

3.0

38

1.0

0.12.0

`atan`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`atan2`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`atanh`

38

12

25

25

8

38

25

25

8

3.0

38

1.0

0.12.0

`cbrt`

38

12

25

25

8

38

25

25

8

3.0

38

1.0

0.12.0

`ceil`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`clz32`

38

12

31

25

7

38

31

25

7

3.0

38

1.0

0.12.0

`cos`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`cosh`

38

12

25

25

8

38

25

25

8

3.0

38

1.0

0.12.0

`exp`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`expm1`

38

12

25

25

8

38

25

25

8

3.0

38

1.0

0.12.0

`floor`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`fround`

38

12

26

25

8

38

26

25

8

3.0

38

1.0

0.12.0

`hypot`

38

12

27

25

8

38

27

25

8

3.0

38

1.0

0.12.0

`imul`

28

12

20

16

7

28

20

15

7

1.5

4.4

1.0

0.12.0

`log`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`log10`

38

12

25

25

8

38

25

25

8

3.0

38

1.0

0.12.0

`log1p`

38

12

25

25

8

38

25

25

8

3.0

38

1.0

0.12.0

`log2`

38

12

25

25

8

38

25

25

8

3.0

38

1.0

0.12.0

`max`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`min`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`pow`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`random`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`round`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`sign`

38

12

25

25

9

38

25

25

9

3.0

38

1.0

0.12.0

`sin`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`sinh`

38

12

25

25

8

38

25

25

8

3.0

38

1.0

0.12.0

`sqrt`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`tan`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`tanh`

38

12

25

25

8

38

25

25

8

3.0

38

1.0

0.12.0

`trunc`

38

12

25

25

8

38

25

25

8

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [`Number`](number)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math>

