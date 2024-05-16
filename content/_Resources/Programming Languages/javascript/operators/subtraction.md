Subtraction (-)
===============

 
The `-` operator subtracts the two operands, producing their difference.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x - y
```




 
Description
-----------

 
The `-` operator is overloaded for two types of operands: number and
[BigInt](../global_objects/bigint). It first [coerces both operands to
numeric
values](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#numeric_coercion)
and tests the types of them. It performs BigInt subtraction if both
operands become BigInts; otherwise, it performs number subtraction. A
[`TypeError`](../global_objects/typeerror) is thrown if one operand
becomes a BigInt but the other becomes a number.



 
Examples
--------


 
### Subtraction with numbers 

 
 
 
[js]


```js
// Number - Number -> subtraction
5 - 3; // 2

// Number - Number -> subtraction
3 - 5; // -2
```




 
### Subtraction with non-numbers 

 
 
 
[js]


```js
// String - Number -> subtraction
"foo" - 3; // NaN; "foo" is converted to the number NaN

// Number - String -> subtraction
5 - "3"; // 2; "3" is converted to the number 3
```




 
### Subtraction with BigInts 

 
 
 
[js]


```js
// BigInt - BigInt -> subtraction
2n - 1n; // 1n
```


You cannot mix BigInt and number operands in subtraction.

 
 
[js]


```js
2n - 1; // TypeError: Cannot mix BigInt and other types, use explicit conversions
2 - 1n; // TypeError: Cannot mix BigInt and other types, use explicit conversions
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-subtraction-operator-minus]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-subtraction-operator-minus)

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

`Subtraction`

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
-   [Division (`/`)](division)
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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Subtraction>

