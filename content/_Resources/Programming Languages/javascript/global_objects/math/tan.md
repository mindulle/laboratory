Math.tan()
==========

 
The `Math.tan()` static method returns the tangent of a number in
radians.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.tan(x)
```




 
### Parameters

 

[`x`](#x)

:   A number representing an angle in radians.



 
### Return value 

 
The tangent of `x`. If `x` is [`Infinity`](../infinity), `-Infinity`, or
[`NaN`](../nan), returns [`NaN`](../nan).

 
**Note:** Due to floating point precision, it\'s not possible to obtain
the exact value π/2, so the result is always finite if not `NaN`.




 
Description
-----------

 
Because `tan()` is a static method of `Math`, you always use it as
`Math.tan()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.tan() 

 
 
 
[js]


```js
Math.tan(-Infinity); // NaN
Math.tan(-0); // -0
Math.tan(0); // 0
Math.tan(1); // 1.5574077246549023
Math.tan(Math.PI / 4); // 0.9999999999999999 (Floating point error)
Math.tan(Infinity); // NaN
```




 
### Math.tan() and π/2 

 
It\'s not possible to calculate `tan(π/2)` exactly.

 
 
[js]


```js
Math.tan(Math.PI / 2); // 16331239353195370
Math.tan(Math.PI / 2 + Number.EPSILON); // -6218431163823738
```




 
### Using Math.tan() with a degree value 

 
Because the `Math.tan()` function accepts radians, but it is often
easier to work with degrees, the following function accepts a value in
degrees, converts it to radians and returns the tangent.

 
 
[js]


```js
function getTanDeg(deg) {
  const rad = (deg * Math.PI) / 180;
  return Math.tan(rad);
}
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.tan]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.tan)

  -----------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [`Math.acos()`](acos)
-   [`Math.asin()`](asin)
-   [`Math.atan()`](atan)
-   [`Math.atan2()`](atan2)
-   [`Math.cos()`](cos)
-   [`Math.sin()`](sin)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/tan>

