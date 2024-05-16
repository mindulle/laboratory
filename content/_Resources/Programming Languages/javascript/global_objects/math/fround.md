Math.fround()
=============

 
The `Math.fround()` static method returns the nearest [32-bit single
precision](https://en.wikipedia.org/wiki/Single-precision_floating-point_format)
float representation of a number.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.fround(doubleFloat)
```




 
### Parameters

 

[`doubleFloat`](#doublefloat)

:   A number.



 
### Return value 

 
The nearest [32-bit single
precision](https://en.wikipedia.org/wiki/Single-precision_floating-point_format)
float representation of `x`.



 
Description
-----------

 
JavaScript uses 64-bit double floating-point numbers internally, which
offer a very high precision. However, sometimes you may be working with
32-bit floating-point numbers, for example if you are reading values
from a [`Float32Array`](../float32array). This can create confusion:
checking a 64-bit float and a 32-bit float for equality may fail even
though the numbers are seemingly identical.

To solve this, `Math.fround()` can be used to cast the 64-bit float to a
32-bit float. Internally, JavaScript continues to treat the number as a
64-bit float, it just performs a \"round to even\" on the 23rd bit of
the mantissa, and sets all following mantissa bits to `0`. If the number
is outside the range of a 32-bit float, [`Infinity`](../infinity) or
`-Infinity` is returned.

Because `fround()` is a static method of `Math`, you always use it as
`Math.fround()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.fround() 

 
The number 1.5 can be precisely represented in the binary numeral
system, and is identical in 32-bit and 64-bit:

 
 
[js]


```js
Math.fround(1.5); // 1.5
Math.fround(1.5) === 1.5; // true
```


However, the number 1.337 cannot be precisely represented in the binary
numeral system, so it differs in 32-bit and 64-bit:

 
 
[js]


```js
Math.fround(1.337); // 1.3370000123977661
Math.fround(1.337) === 1.337; // false
```


$2^{150}$ is too big for a 32-bit float, so `Infinity` is returned:

 
 
[js]


```js
2 ** 150; // 1.42724769270596e+45
Math.fround(2 ** 150); // Infinity
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.fround]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.fround)

  -----------------------------------------------------------------------------------------------------


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

`fround`

38

12

26

25

8

38

26

25

8

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `Math.fround` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [`Math.round()`](round)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/fround>

