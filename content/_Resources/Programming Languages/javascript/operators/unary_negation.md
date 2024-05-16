Unary negation (-)
==================

 
The `-` operator precedes its operand and negates it.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
-x
```




 
Description
-----------

 
The `-` operator is overloaded for two types of operands: number and
[BigInt](../global_objects/bigint). It first [coerces the operand to a
numeric
value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#numeric_coercion)
and tests the type of it. It performs BigInt negation if the operand
becomes a BigInt; otherwise, it performs number negation.



 
Examples
--------


 
### Negating numbers 

 
 
 
[js]


```js
const x = 3;
const y = -x;
// y is -3; x is 3
```




 
### Negating non-numbers 

 
The unary negation operator can convert a non-number into a number.

 
 
[js]


```js
const x = "4";
const y = -x;

// y is -4
```


BigInts can be negated using the unary negation operator.

 
 
[js]


```js
const x = 4n;
const y = -x;

// y is -4n
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-unary-minus-operator]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-unary-minus-operator)

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

`Unary_negation`

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
-   [Division (`/`)](division)
-   [Multiplication (`*`)](multiplication)
-   [Remainder (`%`)](remainder)
-   [Exponentiation (`**`)](exponentiation)
-   [Increment (`++`)](increment)
-   [Decrement (`--`)](decrement)
-   [Unary plus (`+`)](unary_plus)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Unary_negation>

