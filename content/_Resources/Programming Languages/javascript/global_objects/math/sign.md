Math.sign()
===========

 
The `Math.sign()` static method returns 1 or -1, indicating the sign of
the number passed as argument. If the input is 0 or -0, it will be
returned as-is.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.sign(x)
```




 
### Parameters

 

[`x`](#x)

:   A number.



 
### Return value 

 
A number representing the sign of `x`:

-   If `x` is positive, returns `1`.
-   If `x` is negative, returns `-1`.
-   If `x` is positive zero, returns `0`.
-   If `x` is negative zero, returns `-0`.
-   Otherwise, returns [`NaN`](../nan).



 
Description
-----------

 
Because `sign()` is a static method of `Math`, you always use it as
`Math.sign()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.sign() 

 
 
 
[js]


```js
Math.sign(3); // 1
Math.sign(-3); // -1
Math.sign("-3"); // -1
Math.sign(0); // 0
Math.sign(-0); // -0
Math.sign(NaN); // NaN
Math.sign("foo"); // NaN
Math.sign(); // NaN
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.sign]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.sign)

  -------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [Polyfill of `Math.sign` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [`Math.abs()`](abs)
-   [`Math.ceil()`](ceil)
-   [`Math.floor()`](floor)
-   [`Math.round()`](round)
-   [`Math.trunc()`](trunc)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sign>

