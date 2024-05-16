Math.expm1()
============

 
The `Math.expm1()` static method returns [e](e) raised to the power of a
number, subtracted by 1. That is

$${\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{e}\mathtt{x}\mathtt{p}\mathtt{m}\mathtt{1}}(\mathtt{x})} = e^{x} - 1$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.expm1(x)
```




 
### Parameters

 

[`x`](#x)

:   A number.



 
### Return value 

 
A number representing e^x^ - 1, where e is [the base of the natural
logarithm](e).



 
Description
-----------

 
For very small values of *x*, adding 1 can reduce or eliminate
precision. The double floats used in JS give you about 15 digits of
precision. 1 + 1e-15 = 1.000000000000001, but 1 + 1e-16 =
1.000000000000000 and therefore exactly 1.0 in that arithmetic, because
digits past 15 are rounded off.

When you calculate $e^{x}$ where x is a number very close to 0, you
should get an answer very close to 1 + x, because
$\lim\limits_{x\rightarrow 0}\frac{e^{x} - 1}{x} = 1$. If you calculate
`Math.exp(1.1111111111e-15) - 1`, you should get an answer close to
`1.1111111111e-15`. Instead, due to the highest significant figure in
the result of `Math.exp` being the units digit `1`, the final value ends
up being `1.1102230246251565e-15`, with only 3 correct digits. If,
instead, you calculate `Math.exp1m(1.1111111111e-15)`, you will get a
much more accurate answer `1.1111111111000007e-15`, with 11 correct
digits of precision.

Because `expm1()` is a static method of `Math`, you always use it as
`Math.expm1()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.expm1() 

 
 
 
[js]


```js
Math.expm1(-Infinity); // -1
Math.expm1(-1); // -0.6321205588285577
Math.expm1(-0); // -0
Math.expm1(0); // 0
Math.expm1(1); // 1.718281828459045
Math.expm1(Infinity); // Infinity
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.expm1]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.expm1)

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

`expm1`

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

 
-   [Polyfill of `Math.expm1` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [`Math.E`](e)
-   [`Math.exp()`](exp)
-   [`Math.log()`](log)
-   [`Math.log10()`](log10)
-   [`Math.log1p()`](log1p)
-   [`Math.log2()`](log2)
-   [`Math.pow()`](pow)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/expm1>

