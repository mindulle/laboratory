Conditional (ternary) operator
==============================

 
The **conditional (ternary) operator** is the only JavaScript operator
that takes three operands: a condition followed by a question mark
(`?`), then an expression to execute if the condition is
[truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
followed by a colon (`:`), and finally the expression to execute if the
condition is
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy). This
operator is frequently used as an alternative to an
[`if...else`](../statements/if...else) statement.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
condition ? exprIfTrue : exprIfFalse
```




 
### Parameters

 

[`condition`](#condition)

:   An expression whose value is used as a condition.

[`exprIfTrue`](#expriftrue)

:   An expression which is executed if the `condition` evaluates to a
    [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
    value (one which equals or can be converted to `true`).

[`exprIfFalse`](#expriffalse)

:   An expression which is executed if the `condition` is
    [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
    (that is, has a value which can be converted to `false`).



 
Description
-----------

 
Besides `false`, possible falsy expressions are: `null`, `NaN`, `0`, the
empty string (`""`), and `undefined`. If `condition` is any of these,
the result of the conditional expression will be the result of executing
the expression `exprIfFalse`.



 
Examples
--------


 
### A simple example 

 
 
 
[js]


```js
const age = 26;
const beverage = age >= 21 ? "Beer" : "Juice";
console.log(beverage); // "Beer"
```




 
### Handling null values 

 
One common usage is to handle a value that may be `null`:

 
 
[js]


```js
const greeting = (person) => {
  const name = person ? person.name : "stranger";
  return `Howdy, ${name}`;
};

console.log(greeting({ name: "Alice" })); // "Howdy, Alice"
console.log(greeting(null)); // "Howdy, stranger"
```




 
### Conditional chains 

 
The ternary operator is right-associative, which means it can be
\"chained\" in the following way, similar to an
`if … else if … else if … else` chain:

 
 
[js]


```js
function example() {
  return condition1 ? value1
    : condition2 ? value2
    : condition3 ? value3
    : value4;
}
```


This is equivalent to the following
[`if...else`](../statements/if...else) chain.

 
 
[js]


```js
function example() {
  if (condition1) {
    return value1;
  } else if (condition2) {
    return value2;
  } else if (condition3) {
    return value3;
  } else {
    return value4;
  }
}
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-conditional-operator]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-conditional-operator)

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

`Conditional_operator`

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

 
-   [`if...else`](../statements/if...else)
-   [Nullish coalescing operator (`??`)](nullish_coalescing)
-   [Optional chaining (`?.`)](optional_chaining)
-   [Making decisions in your code ---
    conditionals](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals)
-   [Expressions and
    operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_operators)
    guide



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_operator>

