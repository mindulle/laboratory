Math.tanh()
===========

 
The `Math.tanh()` static method returns the hyperbolic tangent of a
number. That is,

$${\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{t}\mathtt{a}\mathtt{n}\mathtt{h}}(\mathtt{x})} = \tanh(x) = \frac{\sinh(x)}{\cosh(x)} = \frac{e^{x} - e^{- x}}{e^{x} + e^{- x}} = \frac{e^{2x} - 1}{e^{2x} + 1}$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.tanh(x)
```




 
### Parameters

 

[`x`](#x)

:   A number.



 
### Return value 

 
The hyperbolic tangent of `x`.



 
Description
-----------

 
Because `tanh()` is a static method of `Math`, you always use it as
`Math.tanh()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.tanh() 

 
 
 
[js]


```js
Math.tanh(-Infinity); // -1
Math.tanh(-0); // -0
Math.tanh(0); // 0
Math.tanh(1); // 0.7615941559557649
Math.tanh(Infinity); // 1
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.tanh]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.tanh)

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

 
See also 
--------

 
-   [Polyfill of `Math.tanh` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [`Math.acosh()`](acosh)
-   [`Math.asinh()`](asinh)
-   [`Math.atanh()`](atanh)
-   [`Math.cosh()`](cosh)
-   [`Math.sinh()`](sinh)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/tanh>

