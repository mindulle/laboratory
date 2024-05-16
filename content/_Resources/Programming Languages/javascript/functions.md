Functions
=========

 
Generally speaking, a function is a \"subprogram\" that can be *called*
by code external (or internal, in the case of recursion) to the
function. Like the program itself, a function is composed of a sequence
of statements called the *function body*. Values can be *passed* to a
function as parameters, and the function will *return* a value.

In JavaScript, functions are [first-class
objects](https://developer.mozilla.org/en-US/docs/Glossary/First-class_Function),
because they can be passed to other functions, returned from functions,
and assigned to variables and properties. They can also have properties
and methods just like any other object. What distinguishes them from
other objects is that functions can be called.

For more examples and explanations, see the [JavaScript guide about
functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions).


 
Description
-----------

 
Function values are typically instances of
[`Function`](global_objects/function). See
[`Function`](global_objects/function) for information on properties and
methods of `Function` objects. Callable values cause
[`typeof`](operators/typeof) to return `"function"` instead of
`"object"`.

 
**Note:** Not all callable values are `instanceof Function`. For
example, the `Function.prototype` object is callable but not an instance
of `Function`. You can also manually set the [prototype
chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
of your function so it no longer inherits from `Function.prototype`.
However, such cases are extremely rare.




 
### Return value 

 
By default, if a function\'s execution doesn\'t end at a
[`return`](statements/return) statement, or if the `return` keyword
doesn\'t have an expression after it, then the return value is
[`undefined`](global_objects/undefined). The `return` statement allows
you to return an arbitrary value from the function. One function call
can only return one value, but you can simulate the effect of returning
multiple values by returning an object or array and
[destructuring](operators/destructuring_assignment) the result.

 
**Note:** Constructors called with [`new`](operators/new) have a
different set of logic to determine their return values.




 
### Passing arguments 

 
[Parameters and
arguments](https://en.wikipedia.org/wiki/Parameter_(computer_programming)#Parameters_and_arguments)
have slightly different meanings, but in MDN web docs, we often use them
interchangeably. For a quick reference:

 
 
[js]


```js
function formatNumber(num) {
  return num.toFixed(2);
}

formatNumber(2);
```


In this example, the `num` variable is called the function\'s
*parameter*: it\'s declared in the parenthesis-enclosed list of the
function\'s definition. The function expects the `num` parameter to be a
number --- although this is not enforceable in JavaScript without
writing runtime validation code. In the `formatNumber(2)` call, the
number `2` is the function\'s *argument*: it\'s the value that is
actually passed to the function in the function call. The argument value
can be accessed inside the function body through the corresponding
parameter name or the [`arguments`](functions/arguments) object.

Arguments are always [*passed by
value*](https://en.wikipedia.org/wiki/Evaluation_strategy#Call_by_reference)
and never *passed by reference*. This means that if a function reassigns
a parameter, the value won\'t change outside the function. More
precisely, object arguments are [*passed by
sharing*](https://en.wikipedia.org/wiki/Evaluation_strategy#Call_by_sharing),
which means if the object\'s properties are mutated, the change will
impact the outside of the function. For example:

 
 
[js]


```js
function updateBrand(obj) {
  // Mutating the object is visible outside the function
  obj.brand = "Toyota";
  // Try to reassign the parameter, but this won't affect
  // the variable's value outside the function
  obj = null;
}

const car = {
  brand: "Honda",
  model: "Accord",
  year: 1998,
};

console.log(car.brand); // Honda

// Pass object reference to the function
updateBrand(car);

// updateBrand mutates car
console.log(car.brand); // Toyota
```


The [`this`](operators/this) keyword refers to the object that the
function is accessed on --- it does not refer to the currently executing
function, so you must refer to the function value by name, even within
the function body.



 
### Defining functions 

 
Broadly speaking, JavaScript has four kinds of functions:

-   Regular function: can return anything; always runs to completion
    after invocation
-   Generator function: returns a
    [`Generator`](global_objects/generator) object; can be paused and
    resumed with the [`yield`](operators/yield) operator
-   Async function: returns a [`Promise`](global_objects/promise); can
    be paused and resumed with the [`await`](operators/await) operator
-   Async generator function: returns an
    [`AsyncGenerator`](global_objects/asyncgenerator) object; both the
    `await` and `yield` operators can be used

For every kind of function, there are three ways to define it:

[Declaration](#declaration)

:   [`function`](statements/function),
    [`function*`](statements/function*),
    [`async function`](statements/async_function),
    [`async function*`](statements/async_function*)

[Expression](#expression)

:   [`function`](operators/function),
    [`function*`](operators/function*),
    [`async function`](operators/async_function),
    [`async function*`](operators/async_function*)

[Constructor](#constructor)

:   [`Function()`](global_objects/function/function),
    [`GeneratorFunction()`](global_objects/generatorfunction/generatorfunction),
    [`AsyncFunction()`](global_objects/asyncfunction/asyncfunction),
    [`AsyncGeneratorFunction()`](global_objects/asyncgeneratorfunction/asyncgeneratorfunction)

In addition, there are special syntaxes for defining [arrow
functions](functions/arrow_functions) and
[methods](functions/method_definitions), which provide more precise
semantics for their usage. [Classes](classes) are conceptually not
functions (because they throw an error when called without `new`), but
they also inherit from `Function.prototype` and have
`typeof MyClass === "function"`.

 
 
[js]


```js
// Constructor
const multiply = new Function("x", "y", "return x * y");

// Declaration
function multiply(x, y) {
  return x * y;
} // No need for semicolon here

// Expression; the function is anonymous but assigned to a variable
const multiply = function (x, y) {
  return x * y;
};
// Expression; the function has its own name
const multiply = function funcName(x, y) {
  return x * y;
};

// Arrow function
const multiply = (x, y) => x * y;

// Method
const obj = {
  multiply(x, y) {
    return x * y;
  },
};
```


All syntaxes do approximately the same thing, but there are some subtle
behavior differences.

-   The `Function()` constructor, `function` expression, and `function`
    declaration syntaxes create full-fledged function objects, which can
    be constructed with [`new`](operators/new). However, arrow functions
    and methods cannot be constructed. Async functions, generator
    functions, and async generator functions are not constructible
    regardless of syntax.
-   The `function` declaration creates functions that are
    [*hoisted*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_hoisting).
    Other syntaxes do not hoist the function and the function value is
    only visible after the definition.
-   The arrow function and `Function()` constructor always create
    *anonymous* functions, which means they can\'t easily call
    themselves recursively. One way to call an arrow function
    recursively is by assigning it to a variable.
-   The arrow function syntax does not have access to `arguments` or
    `this`.
-   The `Function()` constructor cannot access any local variables ---
    it only has access to the global scope.
-   The `Function()` constructor causes runtime compilation and is often
    slower than other syntaxes.

For `function` expressions, there is a distinction between the function
name and the variable the function is assigned to. The function name
cannot be changed, while the variable the function is assigned to can be
reassigned. The function name can be different from the variable the
function is assigned to --- they have no relation to each other. The
function name can be used only within the function\'s body. Attempting
to use it outside the function\'s body results in an error (or gets
another value, if the same name is declared elsewhere). For example:

 
 
[js]


```js
const y = function x() {};
console.log(x); // ReferenceError: x is not defined
```


On the other hand, the variable the function is assigned to is limited
only by its scope, which is guaranteed to include the scope in which the
function is declared.

A function declaration also creates a variable with the same name as the
function name. Thus, unlike those defined by function expressions,
functions defined by function declarations can be accessed by their name
in the scope they were defined in, as well as in their own body.

A function defined by `new Function` will dynamically have its source
assembled, which is observable when you serialize it. For example,
`console.log(new Function().toString())` gives:

 
 
[js]


```js
function anonymous(
) {

}
```


This is the actual source used to compile the function. However,
although the `Function()` constructor will create the function with name
`anonymous`, this name is not added to the scope of the body. The body
only ever has access to global variables. For example, the following
would result in an error:

 
 
[js]


```js
new Function("alert(anonymous);")();
```


A function defined by a function expression or by a function declaration
inherits the current scope. That is, the function forms a closure. On
the other hand, a function defined by a `Function` constructor does not
inherit any scope other than the global scope (which all functions
inherit).

 
 
[js]


```js
// p is a global variable
globalThis.p = 5;
function myFunc() {
  // p is a local variable
  const p = 9;

  function decl() {
    console.log(p);
  }
  const expr = function () {
    console.log(p);
  };
  const cons = new Function("\tconsole.log(p);");

  decl();
  expr();
  cons();
}
myFunc();

// Logs:
// 9 (for 'decl' by function declaration (current scope))
// 9 (for 'expr' by function expression (current scope))
// 5 (for 'cons' by Function constructor (global scope))
```


Functions defined by function expressions and function declarations are
parsed only once, while a function defined by the `Function` constructor
parses the string passed to it each and every time the constructor is
called. Although a function expression creates a closure every time, the
function body is not reparsed, so function expressions are still faster
than `new Function(...)`. Therefore the `Function` constructor should
generally be avoided whenever possible.

A function declaration may be unintentionally turned into a function
expression when it appears in an expression context.

 
 
[js]


```js
// A function declaration
function foo() {
  console.log("FOO!");
}

doSomething(
  // A function expression passed as an argument
  function foo() {
    console.log("FOO!");
  },
);
```


On the other hand, a function expression may also be turned into a
function declaration. An [expression
statement](statements/expression_statement) cannot begin with the
`function` or `async function` keywords, which is a common mistake when
implementing
[IIFEs](https://developer.mozilla.org/en-US/docs/Glossary/IIFE)
(Immediately Invoked Function Expressions).

 
 
[js]


```js
function () { // SyntaxError: Function statements require a function name
  console.log("FOO!");
}();

function foo() {
  console.log("FOO!");
}(); // SyntaxError: Unexpected token ')'
```


Instead, start the expression statement with something else, so that the
`function` keyword unambiguously starts a function expression. Common
options include [grouping](operators/grouping) and using
[`void`](operators/void).

 
 
[js]


```js
(function () {
  console.log("FOO!");
})();

void function () {
  console.log("FOO!");
}();
```




 
### Function parameters 

 
Each function parameter is a simple identifier that you can access in
the local scope.

 
 
[js]


```js
function myFunc(a, b, c) {
  // You can access the values of a, b, and c here
}
```


There are three special parameter syntaxes:

-   [*Default parameters*](functions/default_parameters) allow formal
    parameters to be initialized with default values if no value or
    `undefined` is passed.
-   The [*rest parameter*](functions/rest_parameters) allows
    representing an indefinite number of arguments as an array.
-   [*Destructuring*](operators/destructuring_assignment) allows
    unpacking elements from arrays, or properties from objects, into
    distinct variables.

 
 
[js]


```js
function myFunc({ a, b }, c = 1, ...rest) {
  // You can access the values of a, b, c, and rest here
}
```


There are some consequences if one of the above non-simple parameter
syntaxes is used:

-   You cannot apply `"use strict"` to the function body --- this causes
    a [syntax error](errors/strict_non_simple_params).
-   Even if the function is not in [strict mode](strict_mode), the
    [`arguments`](functions/arguments) object stops syncing with the
    named parameters, and
    [`arguments.callee`](functions/arguments/callee) throws an error
    when accessed.



 
### The arguments object 

 
You can refer to a function\'s arguments within the function by using
the [`arguments`](functions/arguments) object.

[`arguments`](functions/arguments)

:   An array-like object containing the arguments passed to the
    currently executing function.

[`arguments.callee`](functions/arguments/callee)

:   The currently executing function.

[`arguments.length`](functions/arguments/length)

:   The number of arguments passed to the function.



 
### Getter and setter functions 

 
You can define accessor properties on any standard built-in object or
user-defined object that supports the addition of new properties. Within
[object literals](operators/object_initializer) and [classes](classes),
you can use special syntaxes to define the getter and setter of an
accessor property.

[get](functions/get)

:   Binds an object property to a function that will be called when that
    property is looked up.

[set](functions/set)

:   Binds an object property to a function to be called when there is an
    attempt to set that property.

Note that these syntaxes create an *object property*, not a *method*.
The getter and setter functions themselves can only be accessed using
reflective APIs such as
[`Object.getOwnPropertyDescriptor()`](global_objects/object/getownpropertydescriptor).



 
### Block-level functions 

 
In [strict mode](strict_mode), functions inside blocks are scoped to
that block. Prior to ES2015, block-level functions were forbidden in
strict mode.

 
 
[js]


```js
"use strict";

function f() {
  return 1;
}

{
  function f() {
    return 2;
  }
}

f() === 1; // true

// f() === 2 in non-strict mode
```




 
### Block-level functions in non-strict code 

 
In a word: **Don\'t.**

In non-strict code, function declarations inside blocks behave
strangely. For example:

 
 
[js]


```js
if (shouldDefineZero) {
  function zero() {
    // DANGER: compatibility risk
    console.log("This is zero.");
  }
}
```


The semantics of this in strict mode are well-specified --- `zero` only
ever exists within that scope of the `if` block. If `shouldDefineZero`
is false, then `zero` should never be defined, since the block never
executes. However, historically, this was left unspecified, so different
browsers implemented it differently in non-strict mode. For more
information, see the [`function`
declaration](statements/function#block-level_function_declaration)
reference.

A safer way to define functions conditionally is to assign a function
expression to a variable:

 
 
[js]


```js
// Using a var makes it available as a global variable,
// with closer behavior to a top-level function declaration
var zero;
if (shouldDefineZero) {
  zero = function () {
    console.log("This is zero.");
  };
}
```




 
Examples
--------


 
### Returning a formatted number 

 
The following function returns a string containing the formatted
representation of a number padded with leading zeros.

 
 
[js]


```js
// This function returns a string padded with leading zeros
function padZeros(num, totalLen) {
  let numStr = num.toString(); // Initialize return value as string
  const numZeros = totalLen - numStr.length; // Calculate no. of zeros
  for (let i = 1; i <= numZeros; i++) {
    numStr = `0${numStr}`;
  }
  return numStr;
}
```


The following statements call the `padZeros` function.

 
 
[js]


```js
let result;
result = padZeros(42, 4); // returns "0042"
result = padZeros(42, 2); // returns "42"
result = padZeros(5, 4); // returns "0005"
```




 
### Determining whether a function exists 

 
You can determine whether a function exists by using the
[`typeof`](operators/typeof) operator. In the following example, a test
is performed to determine if the `window` object has a property called
`noFunc` that is a function. If so, it is used; otherwise, some other
action is taken.

 
 
[js]


```js
if (typeof window.noFunc === "function") {
  // use noFunc()
} else {
  // do something else
}
```


Note that in the `if` test, a reference to `noFunc` is used --- there
are no parentheses `()` after the function name so the actual function
is not called.



Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-function-definitions]](https://tc39.es/ecma262/multipage/ecmascript-language-functions-and-classes.html#sec-function-definitions)

  -----------------------------------------------------------------------------------------------------------------------------------------------


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

`Functions`

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

`arguments`

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

`arrow_functions`

45

12

22\[\"The initial implementation of arrow functions in Firefox made them
automatically strict. This has been changed as of Firefox 24. The use of
`'use strict';` is now required.\", \"Before Firefox 39, a line
terminator (`\\n`) was incorrectly allowed after arrow function
arguments. This has been fixed to conform to the ES2015 specification
and code like `() \\n => {}` will now throw a `SyntaxError` in this and
later versions.\"\]

32

10

45

22\[\"The initial implementation of arrow functions in Firefox made them
automatically strict. This has been changed as of Firefox 24. The use of
`'use strict';` is now required.\", \"Before Firefox 39, a line
terminator (`\\n`) was incorrectly allowed after arrow function
arguments. This has been fixed to conform to the ES2015 specification
and code like `() \\n => {}` will now throw a `SyntaxError` in this and
later versions.\"\]

32

10

5.0

45

1.0

4.0.0

`block_level_functions`

49

12

46

36

10

49

46

36

10

5.0

49

1.0

4.0.0

`default_parameters`

49

14

15

36

10

49

15

36

10

5.0

49

1.0

6.0.0

`get`

1

12

1.5

9.5

3

18

4

14

1

1.0

4.4

1.0

0.10.0

`method_definitions`

39

12

34

26

9

39

34

26

9

4.0

39

1.0

4.0.0

`rest_parameters`

47

12

15

34

10

47

15

34

10

5.0

47

1.0

6.0.0

`set`

1

12

1.5

9.5

3

18

4

14

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
    guide
-   [Classes](classes)
-   [`function`](statements/function)
-   [`function` expression](operators/function)
-   [`Function`](global_objects/function)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions>

