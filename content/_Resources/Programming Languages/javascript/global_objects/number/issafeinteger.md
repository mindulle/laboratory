Number.isSafeInteger()
======================

 
The `Number.isSafeInteger()` static method determines whether the
provided value is a number that is a *safe integer*.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Number.isSafeInteger(testValue)
```




 
### Parameters

 

[`testValue`](#testvalue)

:   The value to be tested for being a safe integer.



 
### Return value 

 
The boolean value `true` if the given value is a number that is a safe
integer. Otherwise `false`.



 
Description
-----------

 
The safe integers consist of all integers from -(2^53^ - 1) to 2^53^ -
1, inclusive (±9,007,199,254,740,991). A safe integer is an integer
that:

-   can be exactly represented as an IEEE-754 double precision number,
    and
-   whose IEEE-754 representation cannot be the result of rounding any
    other integer to fit the IEEE-754 representation.

For example, 2^53^ - 1 is a safe integer: it can be exactly represented,
and no other integer rounds to it under any IEEE-754 rounding mode. In
contrast, 2^53^ is *not* a safe integer: it can be exactly represented
in IEEE-754, but the integer 2^53^ + 1 can\'t be directly represented in
IEEE-754 but instead rounds to 2^53^ under round-to-nearest and
round-to-zero rounding.

Handling values larger or smaller than \~9 quadrillion with full
precision requires using an [arbitrary precision arithmetic
library](https://en.wikipedia.org/wiki/Arbitrary-precision_arithmetic).
See [What Every Programmer Needs to Know about Floating Point
Arithmetic](https://floating-point-gui.de/) for more information on
floating point representations of numbers.

For larger integers, consider using the [`BigInt`](../bigint) type.



 
Examples
--------


 
### Using isSafeInteger() 

 
 
 
[js]


```js
Number.isSafeInteger(3); // true
Number.isSafeInteger(2 ** 53); // false
Number.isSafeInteger(2 ** 53 - 1); // true
Number.isSafeInteger(NaN); // false
Number.isSafeInteger(Infinity); // false
Number.isSafeInteger("3"); // false
Number.isSafeInteger(3.1); // false
Number.isSafeInteger(3.0); // true
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.issafeinteger]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.issafeinteger)

  -----------------------------------------------------------------------------------------------------------------------


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

`isSafeInteger`

34

12

32

21

9

34

32

21

9

2.0

37

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `Number.isSafeInteger` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-number)
-   [`Number`](../number)
-   [`Number.MIN_SAFE_INTEGER`](min_safe_integer)
-   [`Number.MAX_SAFE_INTEGER`](max_safe_integer)
-   [`BigInt`](../bigint)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isSafeInteger>

