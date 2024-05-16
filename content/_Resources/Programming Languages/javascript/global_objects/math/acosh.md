Math.acosh()
============

 
The `Math.acosh()` static method returns the inverse hyperbolic cosine
of a number. That is,

$$\begin{matrix}
{\forall x \geq 1,\;{\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{a}\mathtt{c}\mathtt{o}\mathtt{s}\mathtt{h}}(\mathtt{x})}} & {= \operatorname{arcosh}(x) = \text{the\ unique}y \geq 0\text{such\ that}\cosh(y) = x} \\
{= \ln\left( {x + \sqrt{x^{2} - 1}} \right)} & \\
\end{matrix}$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.acosh(x)
```




 
### Parameters

 

[`x`](#x)

:   A number greater than or equal to 1.



 
### Return value 

 
The inverse hyperbolic cosine of `x`. If `x` is less than 1, returns
[`NaN`](../nan).



 
Description
-----------

 
Because `acosh()` is a static method of `Math`, you always use it as
`Math.acosh()`, rather than as a method of a `Math` object you created
(`Math` is no constructor).



 
Examples
--------


 
### Using Math.acosh() 

 
 
 
[js]


```js
Math.acosh(0); // NaN
Math.acosh(1); // 0
Math.acosh(2); // 1.3169578969248166
Math.acosh(Infinity); // Infinity
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.acosh]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.acosh)

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

`acosh`

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

 
-   [Polyfill of `Math.acosh` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [`Math.asinh()`](asinh)
-   [`Math.atanh()`](atanh)
-   [`Math.cosh()`](cosh)
-   [`Math.sinh()`](sinh)
-   [`Math.tanh()`](tanh)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/acosh>

