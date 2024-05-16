Number.isNaN()
==============

 
The `Number.isNaN()` static method determines whether the passed value
is the number value [`NaN`](../nan), and returns `false` if the input is
not of the Number type. It is a more robust version of the original,
global [`isNaN()`](../isnan) function.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Number.isNaN(value)
```




 
### Parameters

 

[`value`](#value)

:   The value to be tested for [`NaN`](../nan).



 
### Return value 

 
The boolean value `true` if the given value is a number with value
[`NaN`](../nan). Otherwise, `false`.



 
Description
-----------

 
The function `Number.isNaN()` provides a convenient way to check for
equality with `NaN`. Note that you cannot test for equality with `NaN`
using either the [`==`](../../operators/equality) or
[`===`](../../operators/strict_equality) operators, because unlike all
other value comparisons in JavaScript, these evaluate to `false`
whenever one operand is [`NaN`](../nan), even if the other operand is
also [`NaN`](../nan).

Since `x !== x` is only true for `NaN` among all possible JavaScript
values, `Number.isNaN(x)` can also be replaced with a test for
`x !== x`, despite the latter being less readable.

As opposed to the global [`isNaN()`](../isnan) function, the
`Number.isNaN()` method doesn\'t force-convert the parameter to a
number. This makes it safe to pass values that would normally convert to
[`NaN`](../nan) but aren\'t actually the same value as [`NaN`](../nan).
This also means that only values of the Number type that are also
[`NaN`](../nan) return `true`.



 
Examples
--------


 
### Using isNaN() 

 
 
 
[js]


```js
Number.isNaN(NaN); // true
Number.isNaN(Number.NaN); // true
Number.isNaN(0 / 0); // true
Number.isNaN(37); // false
```




 
### Difference between Number.isNaN() and global isNaN() 

 
`Number.isNaN()` doesn\'t attempt to convert the parameter to a number,
so non-numbers always return `false`. The following are all `false`:

 
 
[js]


```js
Number.isNaN("NaN");
Number.isNaN(undefined);
Number.isNaN({});
Number.isNaN("blabla");
Number.isNaN(true);
Number.isNaN(null);
Number.isNaN("37");
Number.isNaN("37.37");
Number.isNaN("");
Number.isNaN(" ");
```


The global [`isNaN()`](../isnan) coerces its parameter to a number:

 
 
[js]


```js
isNaN("NaN"); // true
isNaN(undefined); // true
isNaN({}); // true
isNaN("blabla"); // true
isNaN(true); // false, this is coerced to 1
isNaN(null); // false, this is coerced to 0
isNaN("37"); // false, this is coerced to 37
isNaN("37.37"); // false, this is coerced to 37.37
isNaN(""); // false, this is coerced to 0
isNaN(" "); // false, this is coerced to 0
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.isnan]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.isnan)

  -------------------------------------------------------------------------------------------------------


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

`isNaN`

25

12

15

15

9

25

15

14

9

1.5

4.4

1.0

0.10.0

 
See also 
--------

 
-   [Polyfill of `Number.isNaN` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-number)
-   [`Number`](../number)
-   [`isNaN()`](../isnan)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isNaN>

