AsyncGenerator.prototype.throw()
================================


The `throw()` method of [`AsyncGenerator`](../asyncgenerator) instances
acts as if a `throw` statement is inserted in the generator\'s body at
the current suspended position, which informs the generator of an error
condition and allows it to handle the error, or perform cleanup and
close itself.



Syntax
------




[js]


```js
asyncGeneratorInstance.throw(exception)
```





### Parameters



[`exception`](#exception)

:   The exception to throw. For debugging purposes, it is useful to make
    it an `instanceof` [`Error`](../error).




### Return value 


If the thrown error is not caught, it will return a
[`Promise`](../promise) which rejects with the exception passed in.

If the exception is caught by a
[`try...catch`](../../statements/try...catch) and the generator resumes
to yield more values, it will return a [`Promise`](../promise) which
resolves with an [`Object`](../object) with two properties:

[`done`](#done)

:   A boolean value:

    -   `true` if the generator function\'s control flow has reached the
        end.
    -   `false` if the generator function is able to produce more
        values.

[`value`](#value)

:   The value yielded from the next `yield` expression.




Examples
--------



### Using throw() 


The following example shows a simple generator and an error that is
thrown using the `throw` method. An error can be caught by a
[`try...catch`](../../statements/try...catch) block as usual.



[js]


```js
// An async task. Pretend it's doing something more useful
// in practice.
function sleep(time) {
  return new Promise((resolve, reject) => {
    setTimeout(resolve, time);
  });
}

async function* createAsyncGenerator() {
  while (true) {
    try {
      await sleep(500);
      yield 42;
    } catch (e) {
      console.error(e);
    }
  }
}

const asyncGen = createAsyncGenerator();
asyncGen.next(1).then((res) => console.log(res)); // { value: 42, done: false }
asyncGen
  .throw(new Error("Something went wrong")) // Error: Something went wrong
  .then((res) => console.log(res)); // { value: 42, done: false }
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-asyncgenerator-prototype-throw]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-asyncgenerator-prototype-throw)

  -----------------------------------------------------------------------------------------------------------------------------------------------------


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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncGenerator/throw>

