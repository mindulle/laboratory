Right shift (\>\>)
==================

 
The `>>` operator returns a number or BigInt whose binary representation
is the first operand shifted by the specified number of bits to the
right. Excess bits shifted off to the right are discarded, and copies of
the leftmost bit are shifted in from the left. This operation is also
called \"sign-propagating right shift\" or \"arithmetic right shift\",
because the sign of the resulting number is the same as the sign of the
first operand.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x >> y
```




 
Description
-----------

 
The `>>` operator is overloaded for two types of operands: number and
[BigInt](../global_objects/bigint). For numbers, the operator returns a
32-bit integer. For BigInts, the operator returns a BigInt. It first
[coerces both operands to numeric
values](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#numeric_coercion)
and tests the types of them. It performs BigInt right shift if both
operands become BigInts; otherwise, it converts both operands to [32-bit
integers](../global_objects/number#fixed-width_number_conversion) and
performs number right shift. A
[`TypeError`](../global_objects/typeerror) is thrown if one operand
becomes a BigInt but the other becomes a number.

Since the new leftmost bit has the same value as the previous leftmost
bit, the sign bit (the leftmost bit) does not change. Hence the name
\"sign-propagating\".

The operator operates on the left operand\'s bit representation in
[two\'s complement](https://en.wikipedia.org/wiki/Two's_complement).
Consider the 32-bit binary representations of the decimal (base 10)
numbers `9` and `-9`:

```text
     9 (base 10): 00000000000000000000000000001001 (base 2)
    -9 (base 10): 11111111111111111111111111110111 (base 2)
```

The binary representation under two\'s complement of the negative
decimal (base 10) number `-9` is formed by inverting all the bits of its
opposite number, which is `9` and `00000000000000000000000000001001` in
binary, and adding `1`.

In both cases, the sign of the binary number is given by its leftmost
bit: for the positive decimal number `9`, the leftmost bit of the binary
representation is `0`, and for the negative decimal number `-9`, the
leftmost bit of the binary representation is `1`.

Given those binary representations of the decimal (base 10) numbers `9`,
and `-9`:

`9 >> 2` yields 2:

```text
     9 (base 10): 00000000000000000000000000001001 (base 2)
                  --------------------------------
9 >> 2 (base 10): 00000000000000000000000000000010 (base 2) = 2 (base 10)
```

Notice how two rightmost bits, `01`, have been shifted off, and two
copies of the leftmost bit, `0` have been shifted in from the left.

`-9 >> 2` yields `-3`:

```text
     -9 (base 10): 11111111111111111111111111110111 (base 2)
                   --------------------------------
-9 >> 2 (base 10): 11111111111111111111111111111101 (base 2) = -3 (base 10)
```

Notice how two rightmost bits, `11`, have been shifted off. But as far
as the leftmost bits: in this case, the leftmost bit is `1`. So two
copies of that leftmost `1` bit have been shifted in from the left ---
which preserves the negative sign.

The binary representation `11111111111111111111111111111101` is equal to
the negative decimal (base 10) number `-3`, because all negative
integers are stored as [two\'s
complements](https://en.wikipedia.org/wiki/Two's_complement), and this
one can be calculated by inverting all the bits of the binary
representation of the positive decimal (base 10) number `3`, which is
`00000000000000000000000000000011`, and then adding one.

If the left operand is a number with more than 32 bits, it will get the
most significant bits discarded. For example, the following integer with
more than 32 bits will be converted to a 32-bit integer:

```text
Before: 11100110111110100000000000000110000000000001
After:              10100000000000000110000000000001
```

The right operand will be converted to an unsigned 32-bit integer and
then taken modulo 32, so the actual shift offset will always be a
positive integer between 0 and 31, inclusive. For example, `100 >> 32`
is the same as `100 >> 0` (and produces `100`) because 32 modulo 32 is
0.

For BigInts, there\'s no truncation. Conceptually, understand positive
BigInts as having an infinite number of leading `0` bits, and negative
BigInts having an infinite number of leading `1` bits.

Right shifting any number `x` by `0` returns `x` converted to a 32-bit
integer. Do not use `>> 0` to truncate numbers to integers; use
[`Math.trunc()`](../global_objects/math/trunc#using_bitwise_no-ops_to_truncate_numbers)
instead.



 
Examples
--------


 
### Using right shift 

 
 
 
[js]


```js
9 >> 2; // 2
-9 >> 2; // -3

9n >> 2n; // 2n
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-signed-right-shift-operator]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-signed-right-shift-operator)

  ---------------------------------------------------------------------------------------------------------------------------------------------------


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

`Right_shift`

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
-   [Right shift assignment (`>>=`)](right_shift_assignment)
-   [Unsigned right shift (`>>>`)](unsigned_right_shift)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Right_shift>

