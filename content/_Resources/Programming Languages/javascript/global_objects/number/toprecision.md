Number.prototype.toPrecision()
==============================

 
The `toPrecision()` method of [`Number`](../number) values returns a
string representing this number to the specified precision.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toPrecision()
toPrecision(precision)
```




 
### Parameters

 

[`precision`](#precision) [Optional]

:   An integer specifying the number of significant digits.



 
### Return value 

 
A string representing a [`Number`](../number) object in fixed-point or
exponential notation rounded to `precision` significant digits. See the
discussion of rounding in the description of the
[`Number.prototype.toFixed()`](tofixed) method, which also applies to
`toPrecision()`.

If the `precision` argument is omitted, behaves as
[`Number.prototype.toString()`](tostring). If the `precision` argument
is a non-integer value, it is rounded to the nearest integer.



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if `precision` is not between `1` and `100` (inclusive).



 
Examples
--------


 
### Using `toPrecision` 

 
 
 
[js]


```js
let num = 5.123456;

console.log(num.toPrecision()); // '5.123456'
console.log(num.toPrecision(5)); // '5.1235'
console.log(num.toPrecision(2)); // '5.1'
console.log(num.toPrecision(1)); // '5'

num = 0.000123;

console.log(num.toPrecision()); // '0.000123'
console.log(num.toPrecision(5)); // '0.00012300'
console.log(num.toPrecision(2)); // '0.00012'
console.log(num.toPrecision(1)); // '0.0001'

// note that exponential notation might be returned in some circumstances
console.log((1234.5).toPrecision(2)); // '1.2e+3'
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.prototype.toprecision]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.prototype.toprecision)

  ---------------------------------------------------------------------------------------------------------------------------------------


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

`toPrecision`

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

 
-   [`Number.prototype.toFixed()`](tofixed)
-   [`Number.prototype.toExponential()`](toexponential)
-   [`Number.prototype.toString()`](tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toPrecision>

