Decrement (\--)
===============

 
The `--` operator decrements (subtracts one from) its operand and
returns the value before or after the decrement, depending on where the
operator is placed.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x--
--x
```




 
Description
-----------

 
The `--` operator is overloaded for two types of operands: number and
[BigInt](../global_objects/bigint). It first [coerces the operand to a
numeric
value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#numeric_coercion)
and tests the type of it. It performs BigInt decrement if the operand
becomes a BigInt; otherwise, it performs number decrement.

If used postfix, with operator after operand (for example, `x--`), the
decrement operator decrements and returns the value before decrementing.

If used prefix, with operator before operand (for example, `--x`), the
decrement operator decrements and returns the value after decrementing.

The decrement operator can only be applied on operands that are
references (variables and object properties; i.e. valid [assignment
targets](assignment)). `--x` itself evaluates to a value, not a
reference, so you cannot chain multiple decrement operators together.

 
 
[js]


```js
--(--x); // SyntaxError: Invalid left-hand side expression in prefix operation
```




 
Examples
--------


 
### Postfix decrement 

 
 
 
[js]


```js
let x = 3;
const y = x--;
// x is 2; y is 3

let x2 = 3n;
const y2 = x2--;
// x2 is 2n; y2 is 3n
```




 
### Prefix decrement 

 
 
 
[js]


```js
let x = 3;
const y = --x;
// x is 2; y = 2

let x2 = 3n;
const y2 = --x2;
// x2 is 2n; y2 is 2n
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-postfix-decrement-operator]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-postfix-decrement-operator)

  -------------------------------------------------------------------------------------------------------------------------------------------------


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

`Decrement`

2

12

1

3

4

18

4

10.1

3.2

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
-   [Unary negation (`-`)](unary_negation)
-   [Unary plus (`+`)](unary_plus)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Decrement>

