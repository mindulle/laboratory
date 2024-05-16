async function\* expression
===========================

 
The `async function*` keywords can be used to define an async generator
function inside an expression.

You can also define async generator functions using the
[`async function*` declaration](../statements/async_function*).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
async function* (param0) {
  statements
}
async function* (param0, param1) {
  statements
}
async function* (param0, param1, /* …, */ paramN) {
  statements
}

async function* name(param0) {
  statements
}
async function* name(param0, param1) {
  statements
}
async function* name(param0, param1, /* …, */ paramN) {
  statements
}
```


 
**Note:** An [expression statement](../statements/expression_statement)
cannot begin with the keywords `async function` to avoid ambiguity with
an [`async function*` declaration](../statements/async_function*). The
`async function` keywords only begin an expression when they appear in a
context that cannot accept statements.




 
### Parameters

 

[`name`](#name) [Optional]

:   The function name. Can be omitted, in which case the function is
    *anonymous*. The name is only local to the function body.

[`paramN`](#paramn) [Optional]

:   The name of a formal parameter for the function. For the
    parameters\' syntax, see the [Functions
    reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_parameters).

[`statements`](#statements) [Optional]

:   The statements which comprise the body of the function.



 
Description
-----------

 
An `async function*` expression is very similar to, and has almost the
same syntax as, an [`async function*`
declaration](../statements/async_function*). The main difference between
an `async function*` expression and an `async function*` declaration is
the *function name*, which can be omitted in `async function*`
expressions to create *anonymous* functions. An `async function*`
expression can be used as an
[IIFE](https://developer.mozilla.org/en-US/docs/Glossary/IIFE)
(Immediately Invoked Function Expression) which runs as soon as it is
defined, allowing you to create an ad-hoc [async iterable
object](../iteration_protocols#the_async_iterator_and_async_iterable_protocols).
See also the chapter about [functions](../functions) for more
information.



 
Examples
--------


 
### Using async function\* expression 

 
The following example defines an unnamed asynchronous generator function
and assigns it to `x`. The function yields the square of its argument:

 
 
[js]


```js
const x = async function* (y) {
  yield Promise.resolve(y * y);
};
x(6)
  .next()
  .then((res) => console.log(res.value)); // 36
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-async-generator-function-definitions]](https://tc39.es/ecma262/multipage/ecmascript-language-functions-and-classes.html#sec-async-generator-function-definitions)

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`async_function*`

63

79

55

50

12

63

55

46

12

8.0

63

1.0

10.0.0

 
See also 
--------

 
-   [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
    guide
-   [Functions](../functions)
-   [`async function*`](../statements/async_function*)
-   [`AsyncGeneratorFunction`](../global_objects/asyncgeneratorfunction)
-   [Iteration protocols](../iteration_protocols)
-   [`yield`](yield)
-   [`yield*`](yield*)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/async_function*>

