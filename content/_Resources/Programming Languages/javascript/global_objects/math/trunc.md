Math.trunc()
============

 
The `Math.trunc()` static method returns the integer part of a number by
removing any fractional digits.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.trunc(x)
```




 
### Parameters

 

[`x`](#x)

:   A number.



 
### Return value 

 
The integer part of `x`.



 
Description
-----------

 
Unlike the other three `Math` methods: [`Math.floor()`](floor),
[`Math.ceil()`](ceil) and [`Math.round()`](round), the way
`Math.trunc()` works is very simple. It *truncates* (cuts off) the dot
and the digits to the right of it, no matter whether the argument is a
positive or negative number.

Because `trunc()` is a static method of `Math`, you always use it as
`Math.trunc()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.trunc() 

 
 
 
[js]


```js
Math.trunc(-Infinity); // -Infinity
Math.trunc("-1.123"); // -1
Math.trunc(-0.123); // -0
Math.trunc(-0); // -0
Math.trunc(0); // 0
Math.trunc(0.123); // 0
Math.trunc(13.37); // 13
Math.trunc(42.84); // 42
Math.trunc(Infinity); // Infinity
```




 
### Using bitwise no-ops to truncate numbers 

 
 
**Warning:** This is not a polyfill for `Math.trunc()` because of
non-negligible edge cases.


Bitwise operations convert their operands to 32-bit integers, which
people have historically taken advantage of to truncate float-point
numbers. Common techniques include:

 
 
[js]


```js
const original = 3.14;
const truncated1 = ~~original; // Double negation
const truncated2 = original & -1; // Bitwise AND with -1
const truncated3 = original | 0; // Bitwise OR with 0
const truncated4 = original ^ 0; // Bitwise XOR with 0
const truncated5 = original >> 0; // Bitwise shifting by 0
```


Beware that this is essentially `toInt32`, which is not the same as
`Math.trunc`. When the value does not satisfy -2^31^ - 1 \< `value` \<
2^31^ (-2147483649 \< `value` \< 2147483648), the conversion would
overflow.

 
 
[js]


```js
const a = ~~2147483648; // -2147483648
const b = ~~-2147483649; // 2147483647
const c = ~~4294967296; // 0
```


Only use `~~` as a substitution for `Math.trunc()` when you are
confident that the range of input falls within the range of 32-bit
integers.



Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.trunc]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.trunc)

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

`trunc`

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

 
-   [Polyfill of `Math.trunc` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [`Math.abs()`](abs)
-   [`Math.ceil()`](ceil)
-   [`Math.floor()`](floor)
-   [`Math.round()`](round)
-   [`Math.sign()`](sign)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/trunc>

