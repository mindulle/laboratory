Block statement
===============

 
A **block statement** is used to group zero or more statements. The
block is delimited by a pair of braces (\"curly braces\") and contains a
list of zero or more statements and declarations.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
{
  StatementList
}
```


[`StatementList`](#statementlist)

:   Statements and declarations grouped within the block statement.



 
Description
-----------

 
The block statement is often called the *compound statement* in other
languages. It allows you to use multiple statements where JavaScript
expects only one statement. Combining statements into blocks is a common
practice in JavaScript, especially when used in association with control
flow statements like [`if...else`](if...else) and [`for`](for). The
opposite behavior is possible using an [empty statement](empty), where
you provide no statement, although one is required.

In addition, combined with block-scoped declarations like [`let`](let),
[`const`](const), and [`class`](class), blocks can prevent temporary
variables from polluting the global namespace, just like
[IIFEs](https://developer.mozilla.org/en-US/docs/Glossary/IIFE) do.



 
### Block scoping rules with var or function declaration in non-strict mode 

 
Variables declared with `var` or created by [function
declarations](function) in non-strict mode **do not** have block scope.
Variables introduced within a block are scoped to the containing
function or script, and the effects of setting them persist beyond the
block itself. For example:

 
 
[js]


```js
var x = 1;
{
  var x = 2;
}
console.log(x); // 2
```


This logs 2 because the `var x` statement within the block is in the
same scope as the `var x` statement before the block.

In non-strict code, function declarations inside blocks behave
strangely. Do not use them.



 
### Block scoping rules with let, const, class, or function declaration in strict mode 

 
By contrast, identifiers declared with [`let`](let), [`const`](const),
and [`class`](class) do have block scope:

 
 
[js]


```js
let x = 1;
{
  let x = 2;
}
console.log(x); // 1
```


The `x = 2` is limited in scope to the block in which it was defined.

The same is true of `const`:

 
 
[js]


```js
const c = 1;
{
  const c = 2;
}
console.log(c); // 1; does not throw SyntaxError
```


Note that the block-scoped `const c = 2` *does not* throw a
`SyntaxError: Identifier 'c' has already been declared` because it can
be declared uniquely within the block.

In [strict mode](../strict_mode), function declarations inside blocks
are scoped to that block and are hoisted to the top of the block.

 
 
[js]


```js
"use strict";

{
  foo(); // Logs "foo"
  function foo() {
    console.log("foo");
  }
}

foo(); // ReferenceError: foo is not defined
```




 
Examples
--------


 
### Using a block statement as the body of a for loop 

 
A [`for`](for) loop accepts a single statement as its body.

 
 
[js]


```js
for (let i = 0; i < 10; i++) console.log(i);
```


If you want to use more than one statement in the loop body, you can
group them into one block statement:

 
 
[js]


```js
for (let i = 0; i < 10; i++) {
  console.log(i);
  console.log(i ** 2);
}
```




 
### Using a block statement to encapsulate data 

 
`let` and `const` declarations are scoped to the containing block. This
allows you to hide data from the global scope without wrapping it in a
function.

 
 
[js]


```js
let sector;
{
  // These variables are scoped to this block and are not
  // accessible after the block
  const angle = Math.PI / 3;
  const radius = 10;
  sector = {
    radius,
    angle,
    area: (angle / 2) * radius ** 2,
    perimeter: 2 * radius + angle * radius,
  };
}
console.log(sector);
// {
//   radius: 10,
//   angle: 1.0471975511965976,
//   area: 52.35987755982988,
//   perimeter: 30.471975511965976
// }
console.log(typeof radius); // "undefined"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-block]](https://tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html#sec-block)

  -----------------------------------------------------------------------------------------------------------------------


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

`block`

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

 
-   [`while`](while)
-   [`if...else`](if...else)
-   [`let`](let)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/block>

