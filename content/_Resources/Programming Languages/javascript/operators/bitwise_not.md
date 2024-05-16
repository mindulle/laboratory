Bitwise NOT (\~)
================

 
The `~` operator returns a number or BigInt whose binary representation
has a `1` in each bit position for which the corresponding bit of the
operand is `0`, and a `0` otherwise.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
~x
```




 
Description
-----------

 
The `~` operator is overloaded for two types of operands: number and
[BigInt](../global_objects/bigint). For numbers, the operator returns a
32-bit integer. For BigInts, the operator returns a BigInt. It first
[coerces the operand to a numeric
value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#numeric_coercion)
and tests the type of it. It performs BigInt NOT if the operand becomes
a BigInt; otherwise, it converts the operand to a [32-bit
integer](../global_objects/number#fixed-width_number_conversion) and
performs number bitwise NOT.

The operator operates on the operands\' bit representations in [two\'s
complement](https://en.wikipedia.org/wiki/Two's_complement). The
operator is applied to each bit, and the result is constructed bitwise.

The truth table for the NOT operation is:

 
  x   NOT x
  --- -------
  0   1
  1   0


```text
 9 (base 10) = 00000000000000000000000000001001 (base 2)
               --------------------------------
~9 (base 10) = 11111111111111111111111111110110 (base 2) = -10 (base 10)
```

Numbers with more than 32 bits get their most significant bits
discarded. For example, the following integer with more than 32 bits
will be converted to a 32-bit integer:

```text
Before: 11100110111110100000000000000110000000000001
After:              10100000000000000110000000000001
```

For BigInts, there\'s no truncation. Conceptually, understand positive
BigInts as having an infinite number of leading `0` bits, and negative
BigInts having an infinite number of leading `1` bits.

Bitwise NOTing any 32-bit integer `x` yields `-(x + 1)`. For example,
`~-5` yields `4`.

Bitwise NOTing any number `x` twice returns `x` converted to a 32-bit
integer. Do not use `~~x` to truncate numbers to integers; use
[`Math.trunc()`](../global_objects/math/trunc#using_bitwise_no-ops_to_truncate_numbers)
instead. Due to using 32-bit representation for numbers, both `~-1` and
`~4294967295` (2^32^ - 1) result in `0`.



 
Examples
--------


 
### Using bitwise NOT 

 
 
 
[js]


```js
~0; // -1
~-1; // 0
~1; // -2

~0n; // -1n
~4294967295n; // -4294967296n
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-bitwise-not-operator]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-bitwise-not-operator)

  -------------------------------------------------------------------------------------------------------------------------------------


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

`Bitwise_NOT`

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

 
-   [Bitwise operators in the JS
    guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_operators#bitwise_operators)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_NOT>

