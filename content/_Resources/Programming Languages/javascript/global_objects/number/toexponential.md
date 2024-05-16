Number.prototype.toExponential()
================================

 
The `toExponential()` method of [`Number`](../number) values returns a
string representing this number in exponential notation.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toExponential()
toExponential(fractionDigits)
```




 
### Parameters

 

[`fractionDigits`](#fractiondigits) [Optional]

:   Optional. An integer specifying the number of digits after the
    decimal point. Defaults to as many digits as necessary to specify
    the number.



 
### Return value 

 
A string representing the given [`Number`](../number) object in
exponential notation with one digit before the decimal point, rounded to
`fractionDigits` digits after the decimal point.



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if `fractionDigits` is not between `0` and `100` (inclusive).

[`TypeError`](../typeerror)

:   Thrown if this method is invoked on an object that is not a
    [`Number`](../number).



 
Description
-----------

 
If the `fractionDigits` argument is omitted, the number of digits after
the decimal point defaults to the number of digits necessary to
represent the value uniquely.

If you use the `toExponential()` method for a numeric literal and the
numeric literal has no exponent and no decimal point, leave
whitespace(s) before the dot that precedes the method call to prevent
the dot from being interpreted as a decimal point.

If a number has more digits than requested by the `fractionDigits`
parameter, the number is rounded to the nearest number represented by
`fractionDigits` digits. See the discussion of rounding in the
description of the [`toFixed()`](tofixed) method, which also applies to
`toExponential()`.



 
Examples
--------


 
### Using toExponential 

 
 
 
[js]


```js
const numObj = 77.1234;

console.log(numObj.toExponential()); // 7.71234e+1
console.log(numObj.toExponential(4)); // 7.7123e+1
console.log(numObj.toExponential(2)); // 7.71e+1
console.log((77.1234).toExponential()); // 7.71234e+1
console.log((77).toExponential()); // 7.7e+1
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.prototype.toexponential]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.prototype.toexponential)

  -------------------------------------------------------------------------------------------------------------------------------------------


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

`toExponential`

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

 
-   [Polyfill of `Number.prototype.toExponential` with many bug fixes in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-number)
-   [`Number.prototype.toFixed()`](tofixed)
-   [`Number.prototype.toPrecision()`](toprecision)
-   [`Number.prototype.toString()`](tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toExponential>

