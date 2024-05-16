Function() constructor
======================

 
The `Function()` constructor creates [`Function`](../function) objects.
Calling the constructor directly can create functions dynamically, but
suffers from security and similar (but far less significant) performance
issues as [`eval()`](../eval). However, unlike `eval` (which may have
access to the local scope), the `Function` constructor creates functions
which execute in the global scope only.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Function(functionBody)
new Function(arg1, functionBody)
new Function(arg1, arg2, functionBody)
new Function(arg1, arg2, /* …, */ argN, functionBody)

Function(functionBody)
Function(arg1, functionBody)
Function(arg1, arg2, functionBody)
Function(arg1, arg2, /* …, */ argN, functionBody)
```


 
**Note:** `Function()` can be called with or without
[`new`](../../operators/new). Both create a new `Function` instance.




 
### Parameters

 

[`arg1`](#arg1), ..., `argN` [Optional]

:   Names to be used by the function as formal argument names. Each must
    be a string that corresponds to a valid JavaScript parameter (any of
    plain
    [identifier](https://developer.mozilla.org/en-US/docs/Glossary/Identifier),
    [rest parameter](../../functions/rest_parameters), or
    [destructured](../../operators/destructuring_assignment) parameter,
    optionally with a [default](../../functions/default_parameters)), or
    a list of such strings separated with commas.

    As the parameters are parsed in the same way as function
    expressions, whitespace and comments are accepted. For example:
    `"x", "theValue = 42", "[a, b] /* numbers */"` --- or
    `"x, theValue = 42, [a, b] /* numbers */"`.
    (`"x, theValue = 42", "[a, b]"` is also correct, though very
    confusing to read.)

[`functionBody`](#functionbody)

:   A string containing the JavaScript statements comprising the
    function definition.



 
Description
-----------

 
`Function` objects created with the `Function` constructor are parsed
when the function is created. This is less efficient than creating a
function with a [function expression](../../operators/function) or
[function declaration](../../statements/function) and calling it within
your code, because such functions are parsed with the rest of the code.

All arguments passed to the function, except the last, are treated as
the names of the identifiers of the parameters in the function to be
created, in the order in which they are passed. The function will be
dynamically compiled as a function expression, with the source assembled
in the following fashion:

 
 
[js]


```js
`function anonymous(${args.join(",")}
) {
${functionBody}
}`;
```


This is observable by calling the function\'s [`toString()`](tostring)
method.

However, unlike normal [function expressions](../../operators/function),
the name `anonymous` is not added to the `functionBody`\'s scope, since
`functionBody` only has access the global scope. If `functionBody` is
not in [strict mode](../../strict_mode) (the body itself needs to have
the `"use strict"` directive since it doesn\'t inherit the strictness
from the context), you may use
[`arguments.callee`](../../functions/arguments/callee) to refer to the
function itself. Alternatively, you can define the recursive part as an
inner function:

 
 
[js]


```js
const recursiveFn = new Function(
  "count",
  `
(function recursiveFn(count) {
  if (count < 0) {
    return;
  }
  console.log(count);
  recursiveFn(count - 1);
})(count);
`,
);
```


Note that the two dynamic parts of the assembled source --- the
parameters list `args.join(",")` and `functionBody` --- will first be
parsed separately to ensure they are each syntactically valid. This
prevents injection-like attempts.

 
 
[js]


```js
new Function("/*", "*/) {");
// SyntaxError: Unexpected end of arg string
// Doesn't become "function anonymous(/*) {*/) {}"
```




 
Examples
--------


 
### Specifying arguments with the Function constructor 

 
The following code creates a `Function` object that takes two arguments.

 
 
[js]


```js
// Example can be run directly in your JavaScript console

// Create a function that takes two arguments, and returns the sum of those arguments
const adder = new Function("a", "b", "return a + b");

// Call the function
adder(2, 6);
// 8
```


The arguments `a` and `b` are formal argument names that are used in the
function body, `return a + b`.



 
### Creating a function object from a function declaration or function expression 

 
 
 
[js]


```js
// The function constructor can take in multiple statements separated by a semicolon. Function expressions require a return statement with the function's name

// Observe that new Function is called. This is so we can call the function we created directly afterwards
const sumOfArray = new Function(
  "const sumArray = (arr) => arr.reduce((previousValue, currentValue) => previousValue + currentValue); return sumArray",
)();

// call the function
sumOfArray([1, 2, 3, 4]);
// 10

// If you don't call new Function at the point of creation, you can use the Function.call() method to call it
const findLargestNumber = new Function(
  "function findLargestNumber (arr) { return Math.max(...arr) }; return findLargestNumber",
);

// call the function
findLargestNumber.call({}).call({}, [2, 4, 1, 8, 5]);
// 8

// Function declarations do not require a return statement
const sayHello = new Function(
  "return function (name) { return `Hello, ${name}` }",
)();

// call the function
sayHello("world");
// Hello, world
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-function-constructor]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-function-constructor)

  -------------------------------------------------------------------------------------------------------------------------


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

`Function`

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

 
-   [`function`](../../statements/function)
-   [`function` expression](../../operators/function)
-   [Functions](../../functions)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/Function>

