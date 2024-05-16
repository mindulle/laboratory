Math.round()
============

 
The `Math.round()` static method returns the value of a number rounded
to the nearest integer.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.round(x)
```




 
### Parameters

 

[`x`](#x)

:   A number.



 
### Return value 

 
The value of `x` rounded to the nearest integer.



 
Description
-----------

 
If the fractional portion of the argument is greater than 0.5, the
argument is rounded to the integer with the next higher absolute value.
If it is less than 0.5, the argument is rounded to the integer with the
lower absolute value. If the fractional portion is exactly 0.5, the
argument is rounded to the next integer in the direction of +∞.

 
**Note:** This differs from many languages\' `round()` functions, which
often round half-increments *away from zero*, giving a different result
in the case of negative numbers with a fractional part of exactly 0.5.


`Math.round(x)` is not exactly the same as
[`Math.floor(x + 0.5)`](floor). When `x` is -0, or -0.5 ≤ x \< 0,
`Math.round(x)` returns -0, while `Math.floor(x + 0.5)` returns 0.
However, neglecting that difference and potential precision errors,
`Math.round(x)` and `Math.floor(x + 0.5)` are generally equivalent.

Because `round()` is a static method of `Math`, you always use it as
`Math.round()`, rather than as a method of a `Math` object you created
(`Math` has no constructor).



 
Examples
--------


 
### Using round 

 
 
 
[js]


```js
Math.round(-Infinity); // -Infinity
Math.round(-20.51); // -21
Math.round(-20.5); // -20
Math.round(-0.1); // -0
Math.round(0); // 0
Math.round(20.49); // 20
Math.round(20.5); // 21
Math.round(42); // 42
Math.round(Infinity); // Infinity
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.round]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.round)

  ---------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [`Number.prototype.toPrecision()`](../number/toprecision)
-   [`Number.prototype.toFixed()`](../number/tofixed)
-   [`Math.abs()`](abs)
-   [`Math.ceil()`](ceil)
-   [`Math.floor()`](floor)
-   [`Math.sign()`](sign)
-   [`Math.trunc()`](trunc)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/round>

