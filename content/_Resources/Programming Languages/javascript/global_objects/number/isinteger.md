Number.isInteger()
==================

 
The `Number.isInteger()` static method determines whether the passed
value is an integer.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Number.isInteger(value)
```




 
### Parameters

 

[`value`](#value)

:   The value to be tested for being an integer.



 
### Return value 

 
The boolean value `true` if the given value is an integer. Otherwise
`false`.



 
Description
-----------

 
If the target value is an integer, return `true`, otherwise return
`false`. If the value is [`NaN`](../nan) or [`Infinity`](../infinity),
return `false`. The method will also return `true` for floating point
numbers that can be represented as integer. It will always return
`false` if the value is not a number.

Note that some number literals, while looking like non-integers,
actually represent integers --- due to the precision limit of ECMAScript
floating-point number encoding (IEEE-754). For example,
`5.0000000000000001` only differs from `5` by `1e-16`, which is too
small to be represented. (For reference, [`Number.EPSILON`](epsilon)
stores the distance between 1 and the next representable floating-point
number greater than 1, and that is about `2.22e-16`.) Therefore,
`5.0000000000000001` will be represented with the same encoding as `5`,
thus making `Number.isInteger(5.0000000000000001)` return `true`.

In a similar sense, numbers around the magnitude of
[`Number.MAX_SAFE_INTEGER`](max_safe_integer) will suffer from loss of
precision and make `Number.isInteger` return `true` even when it\'s not
an integer. (The actual threshold varies based on how many bits are
needed to represent the decimal --- for example,
`Number.isInteger(4500000000000000.1)` is `true`, but
`Number.isInteger(4500000000000000.5)` is `false`.)



 
Examples
--------


 
### Using isInteger 

 
 
 
[js]


```js
Number.isInteger(0); // true
Number.isInteger(1); // true
Number.isInteger(-100000); // true
Number.isInteger(99999999999999999999999); // true

Number.isInteger(0.1); // false
Number.isInteger(Math.PI); // false

Number.isInteger(NaN); // false
Number.isInteger(Infinity); // false
Number.isInteger(-Infinity); // false
Number.isInteger("10"); // false
Number.isInteger(true); // false
Number.isInteger(false); // false
Number.isInteger([1]); // false

Number.isInteger(5.0); // true
Number.isInteger(5.000000000000001); // false
Number.isInteger(5.0000000000000001); // true, because of loss of precision
Number.isInteger(4500000000000000.1); // true, because of loss of precision
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.isinteger]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.isinteger)

  ---------------------------------------------------------------------------------------------------------------


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

`isInteger`

34

12

16

21

9

34

16

21

9

2.0

37

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `Number.isInteger` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-number)
-   [`Number`](../number)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isInteger>

