Labeled statement
=================

 
A **labeled statement** is any
[statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements)
that is prefixed with an identifier. You can jump to this label using a
[`break`](break) or [`continue`](continue) statement nested within the
labeled statement.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
label:
  statement
```


[`label`](#label)

:   Any JavaScript [identifier](../lexical_grammar#identifiers) that is
    not a [reserved word](../lexical_grammar#reserved_words).

[`statement`](#statement)

:   A JavaScript statement. `break` can be used within any labeled
    statement, and `continue` can be used within labeled looping
    statements.



 
Description
-----------

 
You can use a label to identify a statement, and later refer to it using
a `break` or `continue` statement. Note that JavaScript has *no* `goto`
statement; you can only use labels with `break` or `continue`.

Any `break` or `continue` that references `label` must be contained
within the `statement` that\'s labeled by `label`. Think about `label`
as a variable that\'s only available in the scope of `statement`.

If a `break label;` statement is encountered when executing `statement`,
execution of `statement` terminates, and execution continues at the
statement immediately following the labeled statement.

`continue label;` can only be used if `statement` is one of the [looping
statements](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements#iterations).
If a `continue label;` statement is encountered when executing
`statement`, execution of `statement` continues at the next iteration of
the loop. `continue;` without a label can only continue the innermost
loop, while `continue label;` allows continuing any given loop even when
the statement is nested within other loops.

A statement can have multiple labels. In this case, the labels are all
functionally equivalent.



 
Examples
--------


 
### Using a labeled continue with for loops 

 
 
 
[js]


```js
// The first for statement is labeled "loop1"
loop1: for (let i = 0; i < 3; i++) {
  // The second for statement is labeled "loop2"
  loop2: for (let j = 0; j < 3; j++) {
    if (i === 1 && j === 1) {
      continue loop1;
    }
    console.log(`i = ${i}, j = ${j}`);
  }
}

// Logs:
// i = 0, j = 0
// i = 0, j = 1
// i = 0, j = 2
// i = 1, j = 0
// i = 2, j = 0
// i = 2, j = 1
// i = 2, j = 2
```


Notice how it skips both \"i = 1, j = 1\" and \"i = 1, j = 2\".



 
### Using a labeled break with for loops 

 
 
 
[js]


```js
let i, j;

// The first for statement is labeled "loop1"
loop1: for (i = 0; i < 3; i++) {
  // The second for statement is labeled "loop2"
  loop2: for (j = 0; j < 3; j++) {
    if (i === 1 && j === 1) {
      break loop1;
    }
    console.log(`i = ${i}, j = ${j}`);
  }
}

// Logs:
// i = 0, j = 0
// i = 0, j = 1
// i = 0, j = 2
// i = 1, j = 0
```


Notice the difference with the previous `continue` example: when
`break loop1` is encountered, the execution of the outer loop is
terminated, so there are no further logs beyond \"i = 1, j = 0\"; when
`continue loop1` is encountered, the execution of the outer loop
continues at the next iteration, so only \"i = 1, j = 1\" and \"i = 1, j
= 2\" are skipped.



 
### Using a labeled continue statement 

 
Given an array of items and an array of tests, this example counts the
number of items that pass all the tests.

 
 
[js]


```js
// Numbers from 1 to 100
const items = Array.from({ length: 100 }, (_, i) => i + 1);
const tests = [
  { pass: (item) => item % 2 === 0 },
  { pass: (item) => item % 3 === 0 },
  { pass: (item) => item % 5 === 0 },
];
let itemsPassed = 0;

itemIteration: for (const item of items) {
  for (const test of tests) {
    if (!test.pass(item)) {
      continue itemIteration;
    }
  }

  itemsPassed++;
}
```


Note how the `continue itemIteration;` statement skips the rest of the
tests for the current item as well as the statement that updates the
`itemsPassed` counter, and continues with the next item. If you don\'t
use a label, you would need to use a boolean flag instead.

 
 
[js]


```js
// Numbers from 1 to 100
const items = Array.from({ length: 100 }, (_, i) => i + 1);
const tests = [
  { pass: (item) => item % 2 === 0 },
  { pass: (item) => item % 3 === 0 },
  { pass: (item) => item % 5 === 0 },
];
let itemsPassed = 0;

for (const item of items) {
  let passed = true;
  for (const test of tests) {
    if (!test.pass(item)) {
      passed = false;
      break;
    }
  }
  if (passed) {
    itemsPassed++;
  }
}
```




 
### Using a labeled break statement 

 
Given an array of items and an array of tests, this example determines
whether all items pass all tests.

 
 
[js]


```js
// Numbers from 1 to 100
const items = Array.from({ length: 100 }, (_, i) => i + 1);
const tests = [
  { pass: (item) => item % 2 === 0 },
  { pass: (item) => item % 3 === 0 },
  { pass: (item) => item % 5 === 0 },
];
let allPass = true;

itemIteration: for (const item of items) {
  for (const test of tests) {
    if (!test.pass(item)) {
      allPass = false;
      break itemIteration;
    }
  }
}
```


Again, if you don\'t use a label, you would need to use a boolean flag
instead.

 
 
[js]


```js
// Numbers from 1 to 100
const items = Array.from({ length: 100 }, (_, i) => i + 1);
const tests = [
  { pass: (item) => item % 2 === 0 },
  { pass: (item) => item % 3 === 0 },
  { pass: (item) => item % 5 === 0 },
];
let allPass = true;

for (const item of items) {
  let passed = true;
  for (const test of tests) {
    if (!test.pass(item)) {
      passed = false;
      break;
    }
  }
  if (!passed) {
    allPass = false;
    break;
  }
}
```




 
### Using a labeled block with break 

 
You can label statements other than loops, such as simple blocks, but
only `break` statements can reference non-loop labels.

 
 
[js]


```js
foo: {
  console.log("face");
  break foo;
  console.log("this will not be executed");
}
console.log("swap");

// Logs:
// "face"
// "swap"
```




 
### Labeled function declarations 

 
Labels can only be applied to [statements, not
declarations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements#difference_between_statements_and_declarations).
There is a legacy grammar that allows function declarations to be
labeled in non-strict code:

 
 
[js]


```js
L: function F() {}
```


In [strict mode](../strict_mode) code, however, this will throw a
[`SyntaxError`](../global_objects/syntaxerror):

 
 
[js]


```js
"use strict";
L: function F() {}
// SyntaxError: functions cannot be labelled
```


Non-plain functions, such as [generator functions](function*) and [async
functions](async_function) can neither be labeled in strict code, nor in
non-strict code:

 
 
[js]


```js
L: function* F() {}
// SyntaxError: generator functions cannot be labelled
```


The labeled function declaration syntax is
[deprecated](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features)
and you should not use it, even in non-strict code. You cannot actually
jump to this label within the function body.



Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-labelled-statements]](https://tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html#sec-labelled-statements)

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

`label`

1

12

1

4

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

 
-   [`break`](break)
-   [`continue`](continue)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/label>

