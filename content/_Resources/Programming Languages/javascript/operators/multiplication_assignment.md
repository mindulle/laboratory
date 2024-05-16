Multiplication assignment (\*=)
===============================

 
The `*=` operator performs [multiplication](multiplication) on the two
operands and assigns the result to the left operand.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x *= y
```




 
Description
-----------

 
`x *= y` is equivalent to `x = x * y`, except that the expression `x` is
only evaluated once.



 
Examples
--------


 
### Using multiplication assignment 

 
 
 
[js]


```js
let bar = 5;

bar *= 2; // 10
bar *= "foo"; // NaN

let foo = 3n;
foo *= 2n; // 6n
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-assignment-operators]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-assignment-operators)

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

`Multiplication_assignment`

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

 
-   [Assignment operators in the JS
    guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_operators#assignment_operators)
-   [Multiplication (`*`)](multiplication)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Multiplication_assignment>

