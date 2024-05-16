Division (/)
============

 
The `/` operator produces the quotient of its operands where the left
operand is the dividend and the right operand is the divisor.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x / y
```




 
Description
-----------

 
The `/` operator is overloaded for two types of operands: number and
[BigInt](../global_objects/bigint). It first [coerces both operands to
numeric
values](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#numeric_coercion)
and tests the types of them. It performs BigInt division if both
operands become BigInts; otherwise, it performs number division. A
[`TypeError`](../global_objects/typeerror) is thrown if one operand
becomes a BigInt but the other becomes a number.

For BigInt division, the result is the quotient of the two operands
truncated towards zero, and the remainder is discarded. A
[`RangeError`](../global_objects/rangeerror) is thrown if the divisor
`y` is `0n`. This is because number division by zero returns `Infinity`
or `-Infinity`, but BigInt has no concept of infinity.



 
Examples
--------


 
### Basic division 

 
 
 
[js]


```js
1 / 2; // 0.5

Math.floor(3 / 2); // 1

1.0 / 2.0; // 0.5

1n / 2n; // 0n
5n / 3n; // 1n
-1n / 3n; // 0n
1n / -3n; // 0n

2n / 2; // TypeError: Cannot mix BigInt and other types, use explicit conversions

// To do division with a BigInt and a non-BigInt, convert either operand
2n / BigInt(2); // 1n
Number(2n) / 2; // 1
```




 
### Division by zero 

 
 
 
[js]


```js
2.0 / 0; // Infinity

2.0 / 0.0; // Infinity, because 0.0 === 0

2.0 / -0.0; // -Infinity

2n / 0n; // RangeError: Division by zero
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-multiplicative-operators]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-multiplicative-operators)

  ---------------------------------------------------------------------------------------------------------------------------------------------


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

`Division`

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

 
-   [Addition (`+`)](addition)
-   [Subtraction (`-`)](subtraction)
-   [Multiplication (`*`)](multiplication)
-   [Remainder (`%`)](remainder)
-   [Exponentiation (`**`)](exponentiation)
-   [Increment (`++`)](increment)
-   [Decrement (`--`)](decrement)
-   [Unary negation (`-`)](unary_negation)
-   [Unary plus (`+`)](unary_plus)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Division>

