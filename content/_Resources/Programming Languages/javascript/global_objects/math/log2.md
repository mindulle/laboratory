Math.log2()
===========

 
The `Math.log2()` static method returns the base 2 logarithm of a
number. That is

$$\forall x > 0,\;{\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{l}\mathtt{o}\mathtt{g}\mathtt{2}}(\mathtt{x})} = \log_{2}(x) = \text{the\ unique}y\text{such\ that}2^{y} = x$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.log2(x)
```




 
### Parameters

 

[`x`](#x)

:   A number greater than or equal to 0.



 
### Return value 

 
The base 2 logarithm of `x`. If `x < 0`, returns [`NaN`](../nan).



 
Description
-----------

 
Because `log2()` is a static method of `Math`, you always use it as
`Math.log2()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).

This function is the equivalent of `Math.log(x) / Math.log(2)`. For
`log2(e)`, use the constant [`Math.LOG2E`](log2e), which is 1 /
[`Math.LN2`](ln2).



 
Examples
--------


 
### Using Math.log2() 

 
 
 
[js]


```js
Math.log2(-2); // NaN
Math.log2(-0); // -Infinity
Math.log2(0); // -Infinity
Math.log2(1); // 0
Math.log2(2); // 1
Math.log2(3); // 1.584962500721156
Math.log2(1024); // 10
Math.log2(Infinity); // Infinity
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.log2]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.log2)

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

`log2`

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

 
-   [Polyfill of `Math.log2` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [`Math.exp()`](exp)
-   [`Math.log()`](log)
-   [`Math.log10()`](log10)
-   [`Math.log1p()`](log1p)
-   [`Math.pow()`](pow)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/log2>

