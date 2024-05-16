AsyncGenerator.prototype.return()
=================================


The `return()` method of [`AsyncGenerator`](../asyncgenerator) instances
acts as if a `return` statement is inserted in the generator\'s body at
the current suspended position, which finishes the generator and allows
the generator to perform any cleanup tasks when combined with a
[`try...finally`](../../statements/try...catch#the_finally_block) block.



Syntax
------




[js]


```js
asyncGeneratorInstance.return()
asyncGeneratorInstance.return(value)
```





### Parameters



[`value`](#value) [Optional]

:   The value to return.




### Return value 


A [`Promise`](../promise) which resolves with an [`Object`](../object)
with two properties:

[`done`](#done)

:   A boolean value:

    -   `true` if the generator function\'s control flow has reached the
        end.
    -   `false` if the generator function\'s control flow hasn\'t
        reached the end and can produce more values. This can only
        happen if the `return` is captured in a
        [`try...finally`](../../statements/try...catch#the_finally_block)
        and there are more `yield` expressions in the `finally` block.

[`value`](#value_2)

:   The value that is given as an argument, or, if the `yield`
    expression is wrapped in a
    [`try...finally`](../../statements/try...catch#the_finally_block),
    the value yielded/returned from the `finally` block.




Description
-----------


The `return()` method, when called, can be seen as if a `return value;`
statement is inserted in the generator\'s body at the current suspended
position, where `value` is the value passed to the `return()` method.
Therefore, in a typical flow, calling `return(value)` will return
`{ done: true, value: value }`. However, if the `yield` expression is
wrapped in a `try...finally` block, the control flow doesn\'t exit the
function body, but proceeds to the `finally` block instead. In this
case, the value returned may be different, and `done` may even be
`false`, if there are more `yield` expressions within the `finally`
block.




Examples
--------



### Using return() 


The following example shows a simple async generator and the `return`
method.



[js]


```js
// An async task. Pretend it's doing something more useful
// in practice.
function delayedValue(time, value) {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve(value), time);
  });
}

async function* createAsyncGenerator() {
  yield delayedValue(500, 1);
  yield delayedValue(500, 2);
  yield delayedValue(500, 3);
}

const asyncGen = createAsyncGenerator();
asyncGen.next().then((res) => console.log(res)); // { value: 1, done: false }
asyncGen.return("foo").then((res) => console.log(res)); // { value: "foo", done: true }
asyncGen.next().then((res) => console.log(res)); // { value: undefined, done: true }
```





### Using return() once a generator is complete 


If no `value` argument is passed into the `return()` method, the promise
will resolve as if the [next()](next) method has been called. In this
example the generator has completed, so the value returned is
`undefined`.

`return()` can still be called after the generator is in a \"completed\"
state, however the generator will stay in this state.



[js]


```js
async function* createAsyncGenerator() {
  yield await Promise.resolve(1);
  yield await Promise.resolve(2);
  yield await Promise.resolve(3);
}
const asyncGen = createAsyncGenerator();
asyncGen.next().then((res) => console.log(res)); // { value: 1, done: false }
asyncGen.next().then((res) => console.log(res)); // { value: 2, done: false }
asyncGen.next().then((res) => console.log(res)); // { value: 3, done: false }
// value is returned undefined, as no value is passed and generator is 'done'
asyncGen.return().then((res) => console.log(res)); // { value: undefined, done: true }
// we can still return a value once the generator is complete
asyncGen.return(1).then((res) => console.log(res)); // { value: 1, done: true }
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-asyncgenerator-prototype-return]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-asyncgenerator-prototype-return)

  -------------------------------------------------------------------------------------------------------------------------------------------------------


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

`return`

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


-   [`async function*`](../../statements/async_function*)
-   [Iterators and
    generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators)
    guide




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncGenerator/return>

