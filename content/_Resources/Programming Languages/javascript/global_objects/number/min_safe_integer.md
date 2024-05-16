Number.MIN\_SAFE\_INTEGER
=========================

 
The `Number.MIN_SAFE_INTEGER` static data property represents the
minimum safe integer in JavaScript, or -(2^53^ - 1).

To represent integers smaller than this, consider using
[`BigInt`](../bigint).


 
Try it 
------

 



 
Value
-----

 
`-9007199254740991` (-9,007,199,254,740,991, or about -9 quadrillion).

 
Property attributes of `Number.MIN_SAFE_INTEGER`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
[Double precision floating point
format](https://en.wikipedia.org/wiki/Double_precision_floating-point_format)
only has 52 bits to represent the [mantissa](../number#number_encoding),
so it can only safely represent integers between -(2^53^ -- 1) and 2^53^
-- 1. Safe in this context refers to the ability to represent integers
exactly and to correctly compare them. For example,
`Number.MIN_SAFE_INTEGER - 1 === Number.MIN_SAFE_INTEGER - 2` will
evaluate to true, which is mathematically incorrect. See
[`Number.isSafeInteger()`](issafeinteger) for more information.

Because `MIN_SAFE_INTEGER` is a static property of
[`Number`](../number), you always use it as `Number.MIN_SAFE_INTEGER`,
rather than as a property of a number value.



 
Examples
--------


 
### Using MIN\_SAFE\_INTEGER 

 
 
 
[js]


```js
Number.MIN_SAFE_INTEGER; // -9007199254740991
-(2 ** 53 - 1); // -9007199254740991
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.min\_safe\_integer]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.min_safe_integer)

  -------------------------------------------------------------------------------------------------------------------------------


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

`MIN_SAFE_INTEGER`

34

12

31

21

9

34

31

21

9

2.0

37

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `Number.MIN_SAFE_INTEGER` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-number)
-   [`Number.MAX_SAFE_INTEGER`](max_safe_integer)
-   [`Number.isSafeInteger()`](issafeinteger)
-   [`BigInt`](../bigint)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/MIN_SAFE_INTEGER>

