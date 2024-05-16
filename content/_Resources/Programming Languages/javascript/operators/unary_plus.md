Unary plus (+)
==============

 
The `+` operator precedes its operand and evaluates to its operand but
attempts to [convert it into a
number](../global_objects/number#number_coercion), if it isn\'t already.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
+x
```




 
Description
-----------

 
Although unary negation (`-`) also can convert non-numbers, unary plus
is the fastest and preferred way of converting something into a number,
because it does not perform any other operations on the number.

Unary plus does the exact same steps as normal [number
coercion](../global_objects/number#number_coercion) used by most
built-in methods expecting numbers. It can convert string
representations of integers and floats, as well as the non-string values
`true`, `false`, and `null`. Integers in both decimal and hexadecimal
(`0x`-prefixed) formats are supported. Negative numbers are supported
(though not for hex). If it cannot parse a particular value, it will
evaluate to [`NaN`](../global_objects/nan). Unlike other arithmetic
operators, which work with both numbers and
[BigInts](../global_objects/bigint), using the `+` operator on BigInt
values throws a [`TypeError`](../global_objects/typeerror).



 
Examples
--------


 
### Usage with numbers 

 
 
 
[js]


```js
const x = 1;
const y = -1;

console.log(+x);
// 1
console.log(+y);
// -1
```




 
### Usage with non-numbers 

 
 
 
[js]


```js
+true  // 1
+false // 0
+null  // 0
+[]    // 0
+function (val) { return val; } // NaN
+1n    // throws TypeError: Cannot convert BigInt value to number
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-unary-plus-operator]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-unary-plus-operator)

  -----------------------------------------------------------------------------------------------------------------------------------


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

`Unary_plus`

1

12

1

4

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

 
-   [Addition (`+`)](addition)
-   [Subtraction (`-`)](subtraction)
-   [Division (`/`)](division)
-   [Multiplication (`*`)](multiplication)
-   [Remainder (`%`)](remainder)
-   [Exponentiation (`**`)](exponentiation)
-   [Increment (`++`)](increment)
-   [Decrement (`--`)](decrement)
-   [Unary negation (`-`)](unary_negation)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Unary_plus>

