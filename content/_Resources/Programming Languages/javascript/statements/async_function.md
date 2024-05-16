async function\*
================

 
The `async function*` declaration creates a
[binding](https://developer.mozilla.org/en-US/docs/Glossary/Binding) of
a new async generator function to a given name.

You can also define async generator functions using the
[`async function*` expression](../operators/async_function*).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
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


 
**Note:** Async generator functions do not have arrow function
counterparts.


 
**Note:** `function` and `*` are separate tokens, so they can be
separated by [whitespace or line
terminators](../lexical_grammar#white_space). However, there cannot be a
line terminator between `async` and `function`, otherwise a semicolon is
[automatically
inserted](../lexical_grammar#automatic_semicolon_insertion), causing
`async` to become an identifier and the rest to become a `function*`
declaration.




 
### Parameters

 

[`name`](#name)

:   The function name.

[`param`](#param) [Optional]

:   The name of a formal parameter for the function. For the
    parameters\' syntax, see the [Functions
    reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_parameters).

[`statements`](#statements) [Optional]

:   The statements comprising the body of the function.



 
Description
-----------

 
An `async function*` declaration creates an
[`AsyncGeneratorFunction`](../global_objects/asyncgeneratorfunction)
object. Each time when an async generator function is called, it returns
a new [`AsyncGenerator`](../global_objects/asyncgenerator) object, which
conforms to the [async iterator
protocol](../iteration_protocols#the_async_iterator_and_async_iterable_protocols).
Every call to `next()` returns a [`Promise`](../global_objects/promise)
that resolves to the iterator result object.

An async generator function combines the features of [async
functions](async_function) and [generator functions](function*). You can
use both the [`await`](../operators/await) and
[`yield`](../operators/yield) keywords within the function body. This
empowers you to handle asynchronous tasks ergonomically with `await`,
while leveraging the lazy nature of generator functions.

When a promise is yielded from an async generator, the iterator result
promise\'s eventual state will match that of the yielded promise. For
example:

 
 
[js]


```js
async function* foo() {
  yield Promise.reject(1);
}

foo()
  .next()
  .catch((e) => console.error(e));
```


`1` will be logged, because if the yielded promise rejects, the iterator
result will reject as well. The `value` property of an async
generator\'s resolved result will not be another promise.

`async function*` declarations behave similar to [`function`](function)
declarations --- they are
[hoisted](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting) to
the top of their scope and can be called anywhere in their scope, and
they can be redeclared only in certain contexts.



 
Examples
--------


 
### Declaring an async generator function 

 
Async generator functions always produce promises of results --- even
when each `yield` step is synchronous.

 
 
[js]


```js
async function* myGenerator(step) {
  await new Promise((resolve) => setTimeout(resolve, 10));
  yield 0;
  yield step;
  yield step * 2;
}

const gen = myGenerator(2);
gen
  .next()
  .then((res) => {
    console.log(res); // { value: 0, done: false }
    return gen.next();
  })
  .then((res) => {
    console.log(res); // { value: 2, done: false }
    return gen.next();
  })
  .then((res) => {
    console.log(res); // { value: 4, done: false }
    return gen.next();
  })
  .then((res) => {
    console.log(res); // { value: undefined, done: true }
    return gen.next();
  });
```




 
### Using an async generator function to read a series of files 

 
In this example, we read a series of files and only access its content
when requested, using Node\'s
[`fs/promises`](https://nodejs.org/dist/latest-v18.x/docs/api/fs.html)
module.

 
 
[js]


```js
async function* readFiles(directory) {
  const files = await fs.readdir(directory);
  for (const file of files) {
    const stats = await fs.stat(file);
    if (stats.isFile()) {
      yield {
        name: file,
        content: await fs.readFile(file, "utf8"),
      };
    }
  }
}

const files = readFiles(".");
console.log((await files.next()).value);
// Possible output: { name: 'file1.txt', content: '...' }
console.log((await files.next()).value);
// Possible output: { name: 'file2.txt', content: '...' }
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
-   [Iterators and
    generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators)
    guide
-   [Functions](../functions)
-   [`AsyncGeneratorFunction`](../global_objects/asyncgeneratorfunction)
-   [`async function*` expression](../operators/async_function*)
-   [`function`](function)
-   [`function*`](function*)
-   [`async function`](async_function)
-   [Iteration protocols](../iteration_protocols)
-   [`yield`](../operators/yield)
-   [`yield*`](../operators/yield*)
-   [`AsyncGenerator`](../global_objects/asyncgenerator)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function*>

