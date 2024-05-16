Math.sinh()
===========

 
The `Math.sinh()` static method returns the hyperbolic sine of a number.
That is,

$${\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{s}\mathtt{i}\mathtt{n}\mathtt{h}}(\mathtt{x})} = \sinh(x) = \frac{e^{x} - e^{- x}}{2}$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.sinh(x)
```




 
### Parameters

 

[`x`](#x)

:   A number.



 
### Return value 

 
The hyperbolic sine of `x`.



 
Description
-----------

 
Because `sinh()` is a static method of `Math`, you always use it as
`Math.sinh()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.sinh() 

 
 
 
[js]


```js
Math.sinh(-Infinity); // -Infinity
Math.sinh(-0); // -0
Math.sinh(0); // 0
Math.sinh(1); // 1.1752011936438014
Math.sinh(Infinity); // Infinity
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.sinh]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.sinh)

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

 
See also 
--------

 
-   [Polyfill of `Math.sinh` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [`Math.acosh()`](acosh)
-   [`Math.asinh()`](asinh)
-   [`Math.atanh()`](atanh)
-   [`Math.cosh()`](cosh)
-   [`Math.tanh()`](tanh)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sinh>

