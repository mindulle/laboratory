Math.imul()
===========

 
The `Math.imul()` static method returns the result of the C-like 32-bit
multiplication of the two parameters.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.imul(a, b)
```




 
### Parameters

 

[`a`](#a)

:   First number.

[`b`](#b)

:   Second number.



 
### Return value 

 
The result of the C-like 32-bit multiplication of the given arguments.



 
Description
-----------

 
`Math.imul()` allows for 32-bit integer multiplication with C-like
semantics. This feature is useful for projects like
[Emscripten](https://en.wikipedia.org/wiki/Emscripten).

Because `imul()` is a static method of `Math`, you always use it as
`Math.imul()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).

If you use normal JavaScript floating point numbers in `imul()`, you
will experience a degrade in performance. This is because of the costly
conversion from a floating point to an integer for multiplication, and
then converting the multiplied integer back into a floating point.
However, with
[asm.js](https://developer.mozilla.org/en-US/docs/Games/Tools/asm.js),
which allows JIT-optimizers to more confidently use integers in
JavaScript, multiplying two numbers stored internally as integers (which
is only possible with asm.js) with `imul()` could be potentially more
performant.



 
Examples
--------


 
### Using Math.imul() 

 
 
 
[js]


```js
Math.imul(2, 4); // 8
Math.imul(-1, 8); // -8
Math.imul(-2, -2); // 4
Math.imul(0xffffffff, 5); // -5
Math.imul(0xfffffffe, 5); // -10
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.imul]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.imul)

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

`imul`

28

12

20

16

7

28

20

15

7

1.5

4.4

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `Math.imul` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [Emscripten](https://en.wikipedia.org/wiki/Emscripten) on Wikipedia



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/imul>

