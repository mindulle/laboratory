Number.prototype.toFixed()
==========================

 
The `toFixed()` method of [`Number`](../number) values formats this
number using [fixed-point
notation](https://en.wikipedia.org/wiki/Fixed-point_arithmetic).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toFixed()
toFixed(digits)
```




 
### Parameters

 

[`digits`](#digits) [Optional]

:   The number of digits to appear after the decimal point; should be a
    value between `0` and `100`, inclusive. If this argument is omitted,
    it is treated as `0`.



 
### Return value 

 
A string representing the given number using fixed-point notation.



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if `digits` is not between `0` and `100` (inclusive).

[`TypeError`](../typeerror)

:   Thrown if this method is invoked on an object that is not a
    [`Number`](../number).



 
Description
-----------

 
The `toFixed()` method returns a string representation of a number
without using [exponential notation](toexponential) and with exactly
`digits` digits after the decimal point. The number is rounded if
necessary, and the fractional part is padded with zeros if necessary so
that it has the specified length.

If the absolute value of the number is greater or equal to 10^21^, this
method uses the same algorithm as
[`Number.prototype.toString()`](tostring) and returns a string in
exponential notation. `toFixed()` returns `"Infinity"`, `"NaN"`, or
`"-Infinity"` if the value of the number is non-finite.

The output of `toFixed()` may be more precise than
[`toString()`](tostring) for some values, because `toString()` only
prints enough significant digits to distinguish the number from adjacent
number values. For example:

 
 
[js]


```js
(1000000000000000128).toString(); // '1000000000000000100'
(1000000000000000128).toFixed(0); // '1000000000000000128'
```


However, choosing a `digits` precision that\'s too high can return
unexpected results, because decimal fractional numbers cannot be
represented precisely in floating point. For example:

 
 
[js]


```js
(0.3).toFixed(50); // '0.29999999999999998889776975374843459576368331909180'
```




 
Examples
--------


 
### Using toFixed() 

 
 
 
[js]


```js
const numObj = 12345.6789;

numObj.toFixed(); // '12346'; rounding, no fractional part
numObj.toFixed(1); // '12345.7'; it rounds up
numObj.toFixed(6); // '12345.678900'; additional zeros
(1.23e20).toFixed(2); // '123000000000000000000.00'
(1.23e-10).toFixed(2); // '0.00'
(2.34).toFixed(1); // '2.3'
(2.35).toFixed(1); // '2.4'; it rounds up
(2.55).toFixed(1); // '2.5'
// it rounds down as it can't be represented exactly by a float and the
// closest representable float is lower
(2.449999999999999999).toFixed(1); // '2.5'
// it rounds up as it's less than Number.EPSILON away from 2.45.
// This literal actually encodes the same number value as 2.45

(6.02 * 10 ** 23).toFixed(50); // 6.019999999999999e+23; large numbers still use exponential notation
```




 
### Using toFixed() with negative numbers 

 
Because member access has higher
[precedence](../../operators/operator_precedence) than unary minus, you
need to group the negative number expression to get a string.

 
 
[js]


```js
-2.34.toFixed(1); // -2.3, a number
(-2.34).toFixed(1); // '-2.3'
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.prototype.tofixed]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.prototype.tofixed)

  -------------------------------------------------------------------------------------------------------------------------------


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

`toFixed`

1

12

1

7

2

18

4

10.1

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [`Number.prototype.toExponential()`](toexponential)
-   [`Number.prototype.toPrecision()`](toprecision)
-   [`Number.prototype.toString()`](tostring)
-   [`Number.EPSILON`](epsilon)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed>

