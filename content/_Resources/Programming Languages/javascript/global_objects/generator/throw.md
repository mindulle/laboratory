Generator.prototype.throw()
===========================

 
The `throw()` method of [`Generator`](../generator) instances acts as if
a `throw` statement is inserted in the generator\'s body at the current
suspended position, which informs the generator of an error condition
and allows it to handle the error, or perform cleanup and close itself.


 
Syntax
------

 
 
 
[js]


```js
generatorInstance.throw(exception)
```




 
### Parameters

 

[`exception`](#exception)

:   The exception to throw. For debugging purposes, it is useful to make
    it an `instanceof` [`Error`](../error).



 
### Return value 

 
If the thrown exception is caught by a
[`try...catch`](../../statements/try...catch) and the generator resumes
to yield more values, it will return an [`Object`](../object) with two
properties:

[`done`](#done)

:   A boolean value:

    -   `true` if the generator function\'s control flow has reached the
        end.
    -   `false` if the generator function is able to produce more
        values.

[`value`](#value)

:   The value yielded from the next `yield` expression.



 
### Exceptions

 
If the thrown exception is not caught by a `try...catch`, the
`exception` passed to `throw()` will be thrown out from the generator
function.



 
Description
-----------

 
The `throw()` method, when called, can be seen as if a
`throw exception;` statement is inserted in the generator\'s body at the
current suspended position, where `exception` is the exception passed to
the `throw()` method. Therefore, in a typical flow, calling
`throw(exception)` will cause the generator to throw. However, if the
`yield` expression is wrapped in a `try...catch` block, the error may be
caught and control flow can either resume after error handling, or exit
gracefully.



 
Examples
--------


 
### Using throw() 

 
The following example shows a simple generator and an error that is
thrown using the `throw` method. An error can be caught by a
[`try...catch`](../../statements/try...catch) block as usual.

 
 
[js]


```js
function* gen() {
  while (true) {
    try {
      yield 42;
    } catch (e) {
      console.log("Error caught!");
    }
  }
}

const g = gen();
g.next();
// { value: 42, done: false }
g.throw(new Error("Something went wrong"));
// "Error caught!"
// { value: 42, done: false }
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-generator.prototype.throw]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-generator.prototype.throw)

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

`throw`

39

13

26

26

10

39

26

26

10

4.0

39

1.0

4.0.0

 
See also 
--------

 
-   [`function*`](../../statements/function*)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator/throw>

