Bitwise OR (\|)
===============

 
The `|` operator returns a number or BigInt whose binary representation
has a `1` in each bit position for which the corresponding bits of
either or both operands are `1`.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x | y
```




 
Description
-----------

 
The `|` operator is overloaded for two types of operands: number and
[BigInt](../global_objects/bigint). For numbers, the operator returns a
32-bit integer. For BigInts, the operator returns a BigInt. It first
[coerces both operands to numeric
values](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#numeric_coercion)
and tests the types of them. It performs BigInt OR if both operands
become BigInts; otherwise, it converts both operands to [32-bit
integers](../global_objects/number#fixed-width_number_conversion) and
performs number bitwise OR. A [`TypeError`](../global_objects/typeerror)
is thrown if one operand becomes a BigInt but the other becomes a
number.

The operator operates on the operands\' bit representations in [two\'s
complement](https://en.wikipedia.org/wiki/Two's_complement). Each bit in
the first operand is paired with the corresponding bit in the second
operand: *first bit* to *first bit*, *second bit* to *second bit*, and
so on. The operator is applied to each pair of bits, and the result is
constructed bitwise.

The truth table for the OR operation is:

 
  x   y   x OR y
  --- --- --------
  0   0   0
  0   1   1
  1   0   1
  1   1   1


```text
     9 (base 10) = 00000000000000000000000000001001 (base 2)
    14 (base 10) = 00000000000000000000000000001110 (base 2)
                   --------------------------------
14 | 9 (base 10) = 00000000000000000000000000001111 (base 2) = 15 (base 10)
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

Bitwise ORing any number `x` with `0` returns `x` converted to a 32-bit
integer. Do not use `| 0` to truncate numbers to integers; use
[`Math.trunc()`](../global_objects/math/trunc#using_bitwise_no-ops_to_truncate_numbers)
instead.



 
Examples
--------


 
### Using bitwise OR 

 
 
 
[js]


```js
// 9  (00000000000000000000000000001001)
// 14 (00000000000000000000000000001110)

14 | 9;
// 15 (00000000000000000000000000001111)

14n | 9n; // 15n
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  prod-BitwiseORExpression]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#prod-BitwiseORExpression)

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

`Bitwise_OR`

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
-   [Bitwise OR assignment (`|=`)](bitwise_or_assignment)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_OR>

