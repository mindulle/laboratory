Math.log()
==========

 
The `Math.log()` static method returns the natural logarithm (base
[e](e)) of a number. That is

$$\forall x > 0,\;{\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{l}\mathtt{o}\mathtt{g}}(\mathtt{x})} = \ln(x) = \text{the\ unique}y\text{such\ that}e^{y} = x$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.log(x)
```




 
### Parameters

 

[`x`](#x)

:   A number greater than or equal to 0.



 
### Return value 

 
The natural logarithm (base [e](e)) of `x`. If `x` is ±0, returns
[`-Infinity`](../number/negative_infinity). If `x < 0`, returns
[`NaN`](../nan).



 
Description
-----------

 
Because `log()` is a static method of `Math`, you always use it as
`Math.log()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).

If you need the natural log of 2 or 10, use the constants
[`Math.LN2`](ln2) or [`Math.LN10`](ln10). If you need a logarithm to
base 2 or 10, use [`Math.log2()`](log2) or [`Math.log10()`](log10). If
you need a logarithm to other bases, use
`Math.log(x) / Math.log(otherBase)` as in the example below; you might
want to precalculate `1 / Math.log(otherBase)` since multiplication in
`Math.log(x) * constant` is much faster.

Beware that positive numbers very close to 1 can suffer from loss of
precision and make its natural logarithm less accurate. In this case,
you may want to use [`Math.log1p`](log1p) instead.



 
Examples
--------


 
### Using Math.log() 

 
 
 
[js]


```js
Math.log(-1); // NaN
Math.log(-0); // -Infinity
Math.log(0); // -Infinity
Math.log(1); // 0
Math.log(10); // 2.302585092994046
Math.log(Infinity); // Infinity
```




 
### Using Math.log() with a different base 

 
The following function returns the logarithm of `y` with base `x` (i.e.
$\log_{x}y$):

 
 
[js]


```js
function getBaseLog(x, y) {
  return Math.log(y) / Math.log(x);
}
```


If you run `getBaseLog(10, 1000)`, it returns `2.9999999999999996` due
to floating-point rounding, but still very close to the actual answer of
3.



Specifications
--------------

 
  -----------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.log]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.log)

  -----------------------------------------------------------------------------------------------


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

`log`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [`Math.exp()`](exp)
-   [`Math.log1p()`](log1p)
-   [`Math.log10()`](log10)
-   [`Math.log2()`](log2)
-   [`Math.pow()`](pow)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/log>

