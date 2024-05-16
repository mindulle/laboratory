void operator
=============

 
The `void` operator evaluates the given `expression` and then returns
[`undefined`](../global_objects/undefined).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
void expression
```




 
Description
-----------

 
This operator allows evaluating expressions that produce a value into
places where an expression that evaluates to
[`undefined`](../global_objects/undefined) is desired.

The `void` operator is often used merely to obtain the `undefined`
primitive value, usually using `void(0)` (which is equivalent to
`void 0`). In these cases, the global variable
[`undefined`](../global_objects/undefined) can be used.

It should be noted that [the precedence](operator_precedence) of the
`void` operator should be taken into account and that parentheses can
help clarify the resolution of the expression following the `void`
operator:

 
 
[js]


```js
void 2 === "2"; // (void 2) === '2', returns false
void (2 === "2"); // void (2 === '2'), returns undefined
```




 
Examples
--------


 
### Immediately Invoked Function Expressions 

 
When using an [immediately-invoked function
expression](https://developer.mozilla.org/en-US/docs/Glossary/IIFE), the
`function` keyword cannot be at the immediate start of the
[statement](../statements/expression_statement), because that would be
parsed as a [function declaration](../statements/function), and would
generate a syntax error when the parentheses representing invocation is
reached --- if the function is unnamed, it would immediately be a syntax
error if the function is parsed as a declaration.

 
 
[js]


```js
function iife() {
  console.log("Executed!");
}(); // SyntaxError: Unexpected token ')'

function () {
  console.log("Executed!");
}(); // SyntaxError: Function statements require a function name
```


In order for the function to be parsed as an [expression](function), the
`function` keyword has to appear at a position that only accepts
expressions, not statements. This can be achieved be prefixing the
keyword with a [unary
operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_operators#unary_operators),
which only accepts expressions as operands. Function invocation has
higher [precedence](operator_precedence) than unary operators, so it
will be executed first. Its return value (which is almost always
`undefined`) will be passed to the unary operator and then immediately
discarded.

Of all the unary operators, `void` offers the best semantic, because it
clearly signals that the return value of the function invocation should
be discarded.

 
 
[js]


```js
void function () {
  console.log("Executed!");
}();

// Logs "Executed!"
```


This is a bit longer than wrapping the function expression in
parentheses, which has the same effect of forcing the `function` keyword
to be parsed as the start of an expression instead of a statement.

 
 
[js]


```js
(function () {
  console.log("Executed!");
})();
```




 
### JavaScript URIs 

 
When a browser follows a `javascript:` URI, it evaluates the code in the
URI and then replaces the contents of the page with the returned value,
unless the returned value is [`undefined`](../global_objects/undefined).
The `void` operator can be used to return `undefined`. For example:

 
 
[html]


```html
<a href="javascript:void(0);">Click here to do nothing</a>

<a href="javascript:void(document.body.style.backgroundColor='green');">
  Click here for green background
</a>
```


 
**Note:** `javascript:` pseudo protocol is discouraged over other
alternatives, such as unobtrusive event handlers.




 
### Non-leaking Arrow Functions 

 
Arrow functions introduce a short-hand braceless syntax that returns an
expression. This can cause unintended side effects if the expression is
a function call where the returned value changes from `undefined` to
some other value.

For example, if `doSomething()` returns `false` in the code below, the
checkbox will no longer be marked as checked or unchecked when the
checkbox is clicked (setting the handler to `false` disables the default
action).

 
 
[js]


```js
checkbox.onclick = () => doSomething();
```


This is unlikely to be desired behaviour! To be safe, when the return
value of a function is not intended to be used, it can be passed to the
`void` operator to ensure that (for example) changing APIs do not cause
arrow functions\' behaviors to change.

 
 
[js]


```js
checkbox.onclick = () => void doSomething();
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-void-operator]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-void-operator)

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

`void`

1

12

1

4

3.1

18

4

10.1

3

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [`undefined`](../global_objects/undefined)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/void>

