Multiplication (\*)
===================

 
The `*` operator produces the product of the operands.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x * y
```




 
Description
-----------

 
The `*` operator is overloaded for two types of operands: number and
[BigInt](../global_objects/bigint). It first [coerces both operands to
numeric
values](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#numeric_coercion)
and tests the types of them. It performs BigInt multiplication if both
operands become BigInts; otherwise, it performs number multiplication. A
[`TypeError`](../global_objects/typeerror) is thrown if one operand
becomes a BigInt but the other becomes a number.



 
Examples
--------


 
### Multiplication using numbers 

 
 
 
[js]


```js
2 * 2; // 4
-2 * 2; // -4
```




 
### Multiplication with Infinity 

 
 
 
[js]


```js
Infinity * 0; // NaN
Infinity * Infinity; // Infinity
```




 
### Multiplication with non-numbers 

 
 
 
[js]


```js
"foo" * 2; // NaN
"2" * 2; // 4
```




 
### Multiplication using BigInts 

 
 
 
[js]


```js
2n * 2n; // 4n
-2n * 2n; // -4n

2n * 2; // TypeError: Cannot mix BigInt and other types, use explicit conversions

// To multiply a BigInt with a non-BigInt, convert either operand
2n * BigInt(2); // 4n
Number(2n) * 2; // 4
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

`Multiplication`

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
-   [Remainder (`%`)](remainder)
-   [Exponentiation (`**`)](exponentiation)
-   [Increment (`++`)](increment)
-   [Decrement (`--`)](decrement)
-   [Unary negation (`-`)](unary_negation)
-   [Unary plus (`+`)](unary_plus)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Multiplication>

