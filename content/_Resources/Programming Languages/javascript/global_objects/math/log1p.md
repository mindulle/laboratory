Math.log1p()
============

 
The `Math.log1p()` static method returns the natural logarithm (base
[e](e)) of `1 + x`, where `x` is the argument. That is:

$$\forall x > - 1,\;{\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{l}\mathtt{o}\mathtt{g}\mathtt{1}\mathtt{p}}(\mathtt{x})} = \ln(1 + x)$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.log1p(x)
```




 
### Parameters

 

[`x`](#x)

:   A number greater than or equal to -1.



 
### Return value 

 
The natural logarithm (base [e](e)) of `x + 1`. If `x` is -1, returns
[`-Infinity`](../number/negative_infinity). If `x < -1`, returns
[`NaN`](../nan).



 
Description
-----------

 
For very small values of *x*, adding 1 can reduce or eliminate
precision. The double floats used in JS give you about 15 digits of
precision. 1 + 1e-15 = 1.000000000000001, but 1 + 1e-16 =
1.000000000000000 and therefore exactly 1.0 in that arithmetic, because
digits past 15 are rounded off.

When you calculate log(1 + *x*) where *x* is a small positive number,
you should get an answer very close to *x*, because
$\lim\limits_{x\rightarrow 0}\frac{\log(1 + x)}{x} = 1$. If you
calculate `Math.log(1 + 1.1111111111e-15)`, you should get an answer
close to `1.1111111111e-15`. Instead, you will end up taking the
logarithm of `1.00000000000000111022` (the roundoff is in binary, so
sometimes it gets ugly), and get the answer 1.11022...e-15, with only 3
correct digits. If, instead, you calculate
`Math.log1p(1.1111111111e-15)`, you will get a much more accurate answer
`1.1111111110999995e-15`, with 15 correct digits of precision (actually
16 in this case).

If the value of `x` is less than -1, the return value is always
[`NaN`](../nan).

Because `log1p()` is a static method of `Math`, you always use it as
`Math.log1p()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.log1p() 

 
 
 
[js]


```js
Math.log1p(-2); // NaN
Math.log1p(-1); // -Infinity
Math.log1p(-0); // -0
Math.log1p(0); // 0
Math.log1p(1); // 0.6931471805599453
Math.log1p(Infinity); // Infinity
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.log1p]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.log1p)

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

`log1p`

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

 
-   [Polyfill of `Math.log1p` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [`Math.exp()`](exp)
-   [`Math.log()`](log)
-   [`Math.expm1()`](expm1)
-   [`Math.log10()`](log10)
-   [`Math.log2()`](log2)
-   [`Math.pow()`](pow)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/log1p>

