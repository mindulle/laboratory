function\* expression
=====================

 
The `function*` keyword can be used to define a generator function
inside an expression.

You can also define generator functions using the [`function*`
declaration](../statements/function*).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
function* (param0) {
  statements
}
function* (param0, param1) {
  statements
}
function* (param0, param1, /* …, */ paramN) {
  statements
}

function* name(param0) {
  statements
}
function* name(param0, param1) {
  statements
}
function* name(param0, param1, /* …, */ paramN) {
  statements
}
```


 
**Note:** An [expression statement](../statements/expression_statement)
cannot begin with the keyword `function` to avoid ambiguity with a
[`function*` declaration](../statements/function*). The `function`
keyword only begins an expression when it appears in a context that
cannot accept statements.




 
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

 
A `function*` expression is very similar to, and has almost the same
syntax as, a [`function*` declaration](../statements/function*). The
main difference between a `function*` expression and a `function*`
declaration is the *function name*, which can be omitted in `function*`
expressions to create *anonymous* functions. A `function*` expression
can be used as an
[IIFE](https://developer.mozilla.org/en-US/docs/Glossary/IIFE)
(Immediately Invoked Function Expression) which runs as soon as it is
defined, allowing you to create an ad-hoc [iterable iterator
object](../iteration_protocols#the_iterable_protocol). See also the
chapter about [functions](../functions) for more information.



 
Examples
--------


 
### Using function\* expression 

 
The following example defines an unnamed generator function and assigns
it to `x`. The function yields the square of its argument:

 
 
[js]


```js
const x = function* (y) {
  yield y * y;
};
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-generator-function-definitions]](https://tc39.es/ecma262/multipage/ecmascript-language-functions-and-classes.html#sec-generator-function-definitions)

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`function*`

49

12

26

36

10

49

26

36

10

5.0

49

1.0

4.0.0

`trailing_comma`

58

79

52

45

10

58

52

43

10

7.0

58

1.0

8.0.0

 
See also 
--------

 
-   [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
    guide
-   [Functions](../functions)
-   [`function*`](../statements/function*)
-   [`GeneratorFunction`](../global_objects/generatorfunction)
-   [Iteration protocols](../iteration_protocols)
-   [`yield`](yield)
-   [`yield*`](yield*)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function*>

