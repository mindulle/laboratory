Math.exp()
==========

 
The `Math.exp()` static method returns [e](e) raised to the power of a
number. That is

$${\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{e}\mathtt{x}\mathtt{p}}(\mathtt{x})} = e^{x}$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.exp(x)
```




 
### Parameters

 

[`x`](#x)

:   A number.



 
### Return value 

 
A nonnegative number representing e^x^, where e is [the base of the
natural logarithm](e).



 
Description
-----------

 
Because `exp()` is a static method of `Math`, you always use it as
`Math.exp()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).

Beware that `e` to the power of a number very close to 0 will be very
close to 1 and suffer from loss of precision. In this case, you may want
to use [`Math.expm1`](expm1) instead, and obtain a much higher-precision
fractional part of the answer.



 
Examples
--------


 
### Using Math.exp() 

 
 
 
[js]


```js
Math.exp(-Infinity); // 0
Math.exp(-1); // 0.36787944117144233
Math.exp(0); // 1
Math.exp(1); // 2.718281828459045
Math.exp(Infinity); // Infinity
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.exp]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.exp)

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

`exp`

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

 
-   [`Math.E`](e)
-   [`Math.expm1()`](expm1)
-   [`Math.log()`](log)
-   [`Math.log10()`](log10)
-   [`Math.log1p()`](log1p)
-   [`Math.log2()`](log2)
-   [`Math.pow()`](pow)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/exp>

