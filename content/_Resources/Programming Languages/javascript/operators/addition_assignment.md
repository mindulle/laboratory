Addition assignment (+=)
========================

 
The `+=` operator performs [addition](addition) (which is either numeric
addition or string concatenation) on the two operands and assigns the
result to the left operand.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
x += y
```




 
Description
-----------

 
`x += y` is equivalent to `x = x + y`, except that the expression `x` is
only evaluated once.



 
Examples
--------


 
### Using addition assignment 

 
 
 
[js]


```js
let baz = true;

// Boolean + Number -> addition
baz += 1; // 2

// Number + Boolean -> addition
baz += false; // 2
```


 
 
[js]


```js
let foo = "foo";

// String + Boolean -> concatenation
foo += false; // "foofalse"

// String + String -> concatenation
foo += "bar"; // "foofalsebar"
```


 
 
[js]


```js
let bar = 5;

// Number + Number -> addition
bar += 2; // 7

// Number + String -> concatenation
bar += "foo"; // "7foo"
```


 
 
[js]


```js
let x = 1n;

// BigInt + BigInt -> addition
x += 2n; // 3n

// BigInt + Number -> throws TypeError
x += 1; // TypeError: Cannot mix BigInt and other types, use explicit conversions
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

`Addition_assignment`

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
-   [Addition (`+`)](addition)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Addition_assignment>

