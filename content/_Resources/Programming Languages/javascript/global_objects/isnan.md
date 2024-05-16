isNaN()
=======

 
The `isNaN()` function determines whether a value is [`NaN`](nan), first
converting the value to a number if necessary. Because coercion inside
the `isNaN()` function can be [surprising](#description), you may prefer
to use [`Number.isNaN()`](number/isnan).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
isNaN(value)
```




 
### Parameters

 

[`value`](#value)

:   The value to be tested.



 
### Return value 

 
`true` if the given value is [`NaN`](nan) after being [converted to a
number](number#number_coercion); otherwise, `false`.



 
Description
-----------

 
`isNaN()` is a function property of the global object.

For number values, `isNaN()` tests if the number is the value
[`NaN`](nan). When the argument to the `isNaN()` function is not of type
[Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#number_type),
the value is first coerced to a number, and the resulting value is then
compared against [`NaN`](nan).

This behavior of `isNaN()` for non-numeric arguments can be confusing!
For example, an empty string is coerced to 0, while a boolean is coerced
to 0 or 1; both values are intuitively \"not numbers\", but they don\'t
evaluate to `NaN`, so `isNaN()` returns `false`. Therefore, `isNaN()`
answers neither the question \"is the input the floating point
[`NaN`](nan) value\" nor the question \"is the input not a number\".

[`Number.isNaN()`](number/isnan) is a more reliable way to test whether
a value is the number value `NaN` or not. Alternatively, the expression
`x !== x` can be used, and neither of the solutions is subject to the
false positives that make the global `isNaN()` unreliable. To test if a
value is a number, use [`typeof x === "number"`](../operators/typeof).

The `isNaN()` function answers the question \"is the input functionally
equivalent to [`NaN`](nan) when used in a number context\". If
`isNaN(x)` returns `false`, you can use `x` in an arithmetic expression
as if it\'s a valid number that\'s not `NaN`. If `isNaN(x)` returns
`true`, `x` will get coerced to `NaN` and make most arithmetic
expressions return `NaN` (because `NaN` propagates). You can use this,
for example, to test whether an argument to a function is arithmetically
processable (usable \"like\" a number), and handle values that are not
number-like by throwing an error, providing a default value, etc. This
way, you can have a function that makes use of the full versatility
JavaScript provides by implicitly converting values depending on
context.

 
**Note:** The [`+` operator](../operators/addition) performs both number
addition and string concatenation. Therefore, even if `isNaN()` returns
`false` for both operands, the `+` operator may still return a string,
because it\'s not used as an arithmetic operator. For example,
`isNaN("1")` returns `false`, but `"1" + 1` returns `"11"`. To be sure
that you are working with numbers, [coerce the value to a
number](number#number_coercion) and use [`Number.isNaN()`](number/isnan)
to test the result.




 
Examples
--------

 
Note how `isNaN()` returns `true` for values that are not the value
`NaN` but are not numbers either:

 
 
[js]


```js
isNaN(NaN); // true
isNaN(undefined); // true
isNaN({}); // true

isNaN(true); // false
isNaN(null); // false
isNaN(37); // false

// Strings
isNaN("37"); // false: "37" is converted to the number 37 which is not NaN
isNaN("37.37"); // false: "37.37" is converted to the number 37.37 which is not NaN
isNaN("37,5"); // true
isNaN("123ABC"); // true: Number("123ABC") is NaN
isNaN(""); // false: the empty string is converted to 0 which is not NaN
isNaN(" "); // false: a string with spaces is converted to 0 which is not NaN

// Dates
isNaN(new Date()); // false; Date objects can be converted to a number (timestamp)
isNaN(new Date().toString()); // true; the string representation of a Date object cannot be parsed as a number

// Arrays
isNaN([]); // false; the primitive representation is "", which coverts to the number 0
isNaN([1]); // false; the primitive representation is "1"
isNaN([1, 2]); // true; the primitive representation is "1,2", which cannot be parsed as number
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-isnan-number]](https://tc39.es/ecma262/multipage/global-object.html#sec-isnan-number)

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

`isNaN`

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

 
-   [`NaN`](nan)
-   [`Number.isNaN()`](number/isnan)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isNaN>

