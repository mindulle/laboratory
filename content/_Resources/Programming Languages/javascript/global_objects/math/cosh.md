Math.cosh()
===========

 
The `Math.cosh()` static method returns the hyperbolic cosine of a
number. That is,

$${\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{c}\mathtt{o}\mathtt{s}\mathtt{h}}(\mathtt{x})} = \cosh(x) = \frac{e^{x} + e^{- x}}{2}$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.cosh(x)
```




 
### Parameters

 

[`x`](#x)

:   A number.



 
### Return value 

 
The hyperbolic cosine of `x`.



 
Description
-----------

 
Because `cosh()` is a static method of `Math`, you always use it as
`Math.cosh()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.cosh() 

 
 
 
[js]


```js
Math.cosh(-Infinity); // Infinity
Math.cosh(-1); // 1.5430806348152437
Math.cosh(-0); // 1
Math.cosh(0); // 1
Math.cosh(1); // 1.5430806348152437
Math.cosh(Infinity); // Infinity
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.cosh]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.cosh)

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

 
See also 
--------

 
-   [Polyfill of `Math.cosh` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [`Math.acosh()`](acosh)
-   [`Math.asinh()`](asinh)
-   [`Math.atanh()`](atanh)
-   [`Math.sinh()`](sinh)
-   [`Math.tanh()`](tanh)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/cosh>

