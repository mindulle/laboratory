Math.log10()
============

 
The `Math.log10()` static method returns the base 10 logarithm of a
number. That is

$$\forall x > 0,\;{\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{l}\mathtt{o}\mathtt{g}\mathtt{1}\mathtt{0}}(\mathtt{x})} = \log_{10}(x) = \text{the\ unique}y\text{such\ that}10^{y} = x$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.log10(x)
```




 
### Parameters

 

[`x`](#x)

:   A number greater than or equal to 0.



 
### Return value 

 
The base 10 logarithm of `x`. If `x < 0`, returns [`NaN`](../nan).



 
Description
-----------

 
Because `log10()` is a static method of `Math`, you always use it as
`Math.log10()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).

This function is the equivalent of `Math.log(x) / Math.log(10)`. For
`log10(e)`, use the constant [`Math.LOG10E`](log10e), which is 1 /
[`Math.LN10`](ln10).



 
Examples
--------


 
### Using Math.log10() 

 
 
 
[js]


```js
Math.log10(-2); // NaN
Math.log10(-0); // -Infinity
Math.log10(0); // -Infinity
Math.log10(1); // 0
Math.log10(2); // 0.3010299956639812
Math.log10(100000); // 5
Math.log10(Infinity); // Infinity
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.log10]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.log10)

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

`log10`

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

 
-   [Polyfill of `Math.log10` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [`Math.exp()`](exp)
-   [`Math.log()`](log)
-   [`Math.log1p()`](log1p)
-   [`Math.log2()`](log2)
-   [`Math.pow()`](pow)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/log10>

