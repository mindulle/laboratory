Math.atanh()
============

 
The `Math.atanh()` static method returns the inverse hyperbolic tangent
of a number. That is,

$$\begin{matrix}
{\forall x \in ({- 1},1),\;{\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{a}\mathtt{t}\mathtt{a}\mathtt{n}\mathtt{h}}(\mathtt{x})}} & {= \operatorname{artanh}(x) = \text{the\ unique}y\text{such\ that}\tanh(y) = x} \\
{= \frac{1}{2}\,\ln\left( \frac{1 + x}{1 - x} \right)} & \\
\end{matrix}$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.atanh(x)
```




 
### Parameters

 

[`x`](#x)

:   A number between -1 and 1, inclusive.



 
### Return value 

 
The inverse hyperbolic tangent of `x`. If `x` is 1, returns
[`Infinity`](../infinity). If `x` is -1, returns `-Infinity`. If `x` is
less than -1 or greater than 1, returns [`NaN`](../nan).



 
Description
-----------

 
Because `atanh()` is a static method of `Math`, you always use it as
`Math.atanh()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.atanh() 

 
 
 
[js]


```js
Math.atanh(-2); // NaN
Math.atanh(-1); // -Infinity
Math.atanh(-0); // -0
Math.atanh(0); // 0
Math.atanh(0.5); // 0.5493061443340548
Math.atanh(1); // Infinity
Math.atanh(2); // NaN
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.atanh]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.atanh)

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

`atanh`

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

 
-   [Polyfill of `Math.atanh` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [`Math.acosh()`](acosh)
-   [`Math.asinh()`](asinh)
-   [`Math.cosh()`](cosh)
-   [`Math.sinh()`](sinh)
-   [`Math.tanh()`](tanh)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/atanh>

