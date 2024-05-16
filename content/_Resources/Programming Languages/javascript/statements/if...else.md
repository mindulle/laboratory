if\...else
==========

 
The `if...else` statement executes a statement if a specified condition
is [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy).
If the condition is
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy),
another statement in the optional `else` clause will be executed.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
if (condition)
  statement1

// With an else clause
if (condition)
  statement1
else
  statement2
```


[`condition`](#condition)

:   An expression that is considered to be either
    [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
    or [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy).

[`statement1`](#statement1)

:   Statement that is executed if *condition* is
    [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy).
    Can be any statement, including further nested `if` statements. To
    execute multiple statements, use a [block](block) statement
    (`{ /* ... */ }`) to group those statements. To execute no
    statements, use an [empty](empty) statement.

[`statement2`](#statement2)

:   Statement that is executed if `condition` is
    [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) and
    the `else` clause exists. Can be any statement, including block
    statements and further nested `if` statements.



 
Description
-----------

 
Multiple `if...else` statements can be nested to create an `else if`
clause. Note that there is no `elseif` (in one word) keyword in
JavaScript.

 
 
[js]


```js
if (condition1)
  statement1
else if (condition2)
  statement2
else if (condition3)
  statement3
// …
else
  statementN
```


To see how this works, this is how it would look if the nesting were
properly indented:

 
 
[js]


```js
if (condition1)
  statement1
else
  if (condition2)
    statement2
  else
    if (condition3)
      statement3
// …
```


To execute multiple statements within a clause, use a block statement
(`{ /* ... */ }`) to group those statements.

 
 
[js]


```js
if (condition) {
  statements1
} else {
  statements2
}
```


Not using blocks may lead to confusing behavior, especially if the code
is hand-formatted. For example:

 
 
[js]


```js
function checkValue(a, b) {
  if (a === 1)
    if (b === 2)
      console.log("a is 1 and b is 2");
  else
    console.log("a is not 1");
}
```


This code looks innocent --- however, executing `checkValue(1, 3)` will
log \"a is not 1\". This is because in the case of [dangling
else](https://en.wikipedia.org/wiki/Dangling_else), the `else` clause
will be connected to the closest `if` clause. Therefore, the code above,
with proper indentation, would look like:

 
 
[js]


```js
function checkValue(a, b) {
  if (a === 1)
    if (b === 2)
      console.log("a is 1 and b is 2");
    else
      console.log("a is not 1");
}
```


In general, it is a good practice to always use block statements,
especially in code involving nested `if` statements.

 
 
[js]


```js
function checkValue(a, b) {
  if (a === 1) {
    if (b === 2) {
      console.log("a is 1 and b is 2");
    }
  } else {
    console.log("a is not 1");
  }
}
```


Do not confuse the primitive Boolean values `true` and `false` with
truthiness or falsiness of the [`Boolean`](../global_objects/boolean)
object. Any value that is not `false`, `undefined`, `null`, `0`, `-0`,
`NaN`, or the empty string (`""`), and any object, including a Boolean
object whose value is `false`, is considered
[truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy) when
used as the condition. For example:

 
 
[js]


```js
const b = new Boolean(false);
if (b) {
  console.log("b is truthy"); // "b is truthy"
}
```




 
Examples
--------


 
### Using if\...else 

 
 
 
[js]


```js
if (cipherChar === fromChar) {
  result += toChar;
  x++;
} else {
  result += clearChar;
}
```




 
### Using else if 

 
Note that there is no `elseif` syntax in JavaScript. However, you can
write it with a space between `else` and `if`:

 
 
[js]


```js
if (x > 50) {
  /* do something */
} else if (x > 5) {
  /* do something */
} else {
  /* do something */
}
```




 
### Using an assignment as a condition 

 
You should almost never have an `if...else` with an assignment like
`x = y` as a condition:

 
 
[js]


```js
if ((x = y)) {
  // …
}
```


Because unlike [`while`](while) loops, the condition is only evaluated
once, so the assignment is only performed once. The code above is
equivalent to:

 
 
[js]


```js
x = y;
if (x) {
  // …
}
```


Which is much clearer. However, in the rare case you find yourself
wanting to do something like that, the [`while`](while) documentation
has a [Using an assignment as a
condition](while#using_an_assignment_as_a_condition) section with our
recommendations.



Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-if-statement]](https://tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html#sec-if-statement)

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

`if...else`

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

 
-   [`block`](block)
-   [`switch`](switch)
-   [Conditional (ternary) operator](../operators/conditional_operator)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else>

