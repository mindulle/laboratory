Math.asinh()
============

 
The `Math.asinh()` static method returns the inverse hyperbolic sine of
a number. That is,

$$\begin{matrix}
{\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{a}\mathtt{s}\mathtt{i}\mathtt{n}\mathtt{h}}(\mathtt{x})} & {= \operatorname{arsinh}(x) = \text{the\ unique}y\text{such\ that}\sinh(y) = x} \\
{= \ln\left( {x + \sqrt{x^{2} + 1}} \right)} & \\
\end{matrix}$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.asinh(x)
```




 
### Parameters

 

[`x`](#x)

:   A number.



 
### Return value 

 
The inverse hyperbolic sine of `x`.



 
Description
-----------

 
Because `asinh()` is a static method of `Math`, you always use it as
`Math.asinh()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.asinh() 

 
 
 
[js]


```js
Math.asinh(-Infinity); // -Infinity
Math.asinh(-1); // -0.881373587019543
Math.asinh(-0); // -0
Math.asinh(0); // 0
Math.asinh(1); // 0.881373587019543
Math.asinh(Infinity); // Infinity
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.asinh]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.asinh)

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

 
See also 
--------

 
-   [Polyfill of `Math.asinh` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [`Math.acosh()`](acosh)
-   [`Math.atanh()`](atanh)
-   [`Math.cosh()`](cosh)
-   [`Math.sinh()`](sinh)
-   [`Math.tanh()`](tanh)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/asinh>

