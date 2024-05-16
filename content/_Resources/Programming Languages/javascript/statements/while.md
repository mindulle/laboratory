while
=====

 
The `while` statement creates a loop that executes a specified statement
as long as the test condition evaluates to true. The condition is
evaluated before executing the statement.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
while (condition)
  statement
```


[`condition`](#condition)

:   An expression evaluated before each pass through the loop. If this
    condition [evaluates to
    true](https://developer.mozilla.org/en-US/docs/Glossary/Truthy),
    `statement` is executed. When condition [evaluates to
    false](https://developer.mozilla.org/en-US/docs/Glossary/Falsy),
    execution continues with the statement after the `while` loop.

[`statement`](#statement)

:   An optional statement that is executed as long as the condition
    evaluates to true. To execute multiple statements within the loop,
    use a [block](block) statement (`{ /* ... */ }`) to group those
    statements.

    Note: Use the [`break`](break) statement to stop a loop before
    `condition` evaluates to true.



 
Examples
--------


 
### Using while 

 
The following `while` loop iterates as long as `n` is less than three.

 
 
[js]


```js
let n = 0;
let x = 0;

while (n < 3) {
  n++;
  x += n;
}
```


Each iteration, the loop increments `n` and adds it to `x`. Therefore,
`x` and `n` take on the following values:

-   After the first pass: `n` = 1 and `x` = 1
-   After the second pass: `n` = 2 and `x` = 3
-   After the third pass: `n` = 3 and `x` = 6

After completing the third pass, the condition `n` \< 3 is no longer
true, so the loop terminates.



 
### Using an assignment as a condition 

 
In some cases, it can make sense to use an assignment as a condition.
This comes with readability tradeoffs, so there are certain stylistic
recommendations that would make the pattern more obvious for everyone.

Consider the following example, which iterates over a document\'s
comments, logging them to the console.

 
 
[js]


```js
const iterator = document.createNodeIterator(document, NodeFilter.SHOW_COMMENT);
let currentNode;
while (currentNode = iterator.nextNode()) {
  console.log(currentNode.textContent.trim());
}
```


That\'s not completely a good-practice example, due to the following
line specifically:

 
 
[js]


```js
while (currentNode = iterator.nextNode()) {
```


The *effect* of that line is fine --- in that, each time a comment node
is found:

1.  `iterator.nextNode()` returns that comment node, which gets assigned
    to `currentNode`.
2.  The value of `currentNode = iterator.nextNode()` is therefore
    [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy).
3.  So the `console.log()` call executes and the loop continues.

...and then, when there are no more comment nodes in the document:

1.  `iterator.nextNode()` returns [`null`](../operators/null).
2.  The value of `currentNode = iterator.nextNode()` is therefore also
    `null`, which is
    [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy).
3.  So the loop ends.

The problem with this line is: conditions typically use [comparison
operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_operators#comparison_operators)
such as `===`, but the `=` in that line isn\'t a comparison operator ---
instead, it\'s an [assignment
operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_operators#assignment_operators).
So that `=` *looks like* it\'s a typo for `===` --- even though it\'s
*not* actually a typo.

Therefore, in cases like that one, some [code-linting
tools](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Introducing_complete_toolchain#code_linting_tools)
such as ESLint\'s
[`no-cond-assign`](https://eslint.org/docs/latest/rules/no-cond-assign)
rule --- in order to help you catch a possible typo so that you can fix
it --- will report a warning such as the following:

> Expected a conditional expression and instead saw an assignment.

Many style guides recommend more explicitly indicating the intention for
the condition to be an assignment. You can do that minimally by putting
additional parentheses as a [grouping operator](../operators/grouping)
around the assignment:

 
 
[js]


```js
const iterator = document.createNodeIterator(document, NodeFilter.SHOW_COMMENT);
let currentNode;
while ((currentNode = iterator.nextNode())) {
  console.log(currentNode.textContent.trim());
}
```


In fact, this is the style enforced by ESLint\'s `no-cond-assign`\'s
default configuration, as well as [Prettier](https://prettier.io/), so
you\'ll likely see this pattern a lot in the wild.

Some people may further recommend adding a comparison operator to turn
the condition into an explicit comparison:

 
 
[js]


```js
while ((currentNode = iterator.nextNode()) !== null) {
```


There are other ways to write this pattern, such as:

 
 
[js]


```js
while ((currentNode = iterator.nextNode()) && currentNode) {
```


Or, forgoing the idea of using a `while` loop altogether:

 
 
[js]


```js
const iterator = document.createNodeIterator(document, NodeFilter.SHOW_COMMENT);
for (
  let currentNode = iterator.nextNode();
  currentNode;
  currentNode = iterator.nextNode()
) {
  console.log(currentNode.textContent.trim());
}
```


If the reader is sufficiently familiar with the assignment as condition
pattern, all these variations should have equivalent readability.
Otherwise, the last form is probably the most readable, albeit the most
verbose.



Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-while-statement]](https://tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html#sec-while-statement)

  -------------------------------------------------------------------------------------------------------------------------------------------


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

`while`

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

 
-   [`do...while`](do...while)
-   [`for`](for)
-   [`break`](break)
-   [`continue`](continue)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while>

