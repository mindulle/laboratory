AsyncIterator
=============


An `AsyncIterator` object is an object that conforms to the [async
iterator
protocol](../iteration_protocols#the_async_iterator_and_async_iterable_protocols)
by providing a `next()` method that returns a promise fulfilling to an
iterator result object. The `AsyncIterator.prototype` object is a hidden
global object that all built-in async iterators inherit from. It
provides an [`@@asyncIterator`](asynciterator/@@asynciterator) method
that returns the async iterator object itself, making the async iterator
also [async
iterable](../iteration_protocols#the_async_iterator_and_async_iterable_protocols).

Note that `AsyncIterator` is *not* a global object, although it will be
in the future with the [async iterator helpers
proposal](https://github.com/tc39/proposal-async-iterator-helpers). The
`AsyncIterator.prototype` object shared by all built-in async iterators
can be obtained with the following code:



[js]


```js
const AsyncIteratorPrototype = Object.getPrototypeOf(
  Object.getPrototypeOf(Object.getPrototypeOf((async function* () {})())),
);
```




Description
-----------


Currently, the only built-in JavaScript async iterator is the
[`AsyncGenerator`](asyncgenerator) object returned by [async generator
functions](../statements/async_function*). There are some other built-in
async iterators in web API, such as the one of a
[`ReadableStream`](https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream).

Each of these async iterators have a distinct prototype object, which
defines the `next()` method used by the particular async iterator. All
of these prototype objects inherit from `AsyncIterator.prototype`, which
provides am [`@@asyncIterator`](symbol/asynciterator) method that
returns the async iterator object itself, making the async iterator also
[async
iterable](../iteration_protocols#the_async_iterator_and_async_iterable_protocols).

 
**Note:** `AsyncIterator.prototype` does not implement
[`@@iterator`](symbol/iterator), so async iterators are not [sync
iterable](../iteration_protocols#the_iterable_protocol) by default.





Instance methods 
----------------



[`AsyncIterator.prototype[@@asyncIterator]()`](asynciterator/@@asynciterator)

:   Returns the async iterator object itself. This allows async iterator
    objects to also be async iterable.




Examples
--------



### Using an async iterator as an async iterable 


All built-in async iterators are also async iterable, so you can use
them in a `for await...of` loop:



[js]


```js
const asyncIterator = (async function* () {
  yield 1;
  yield 2;
  yield 3;
})();
(async () => {
  for await (const value of asyncIterator) {
    console.log(value);
  }
})();
// Logs: 1, 2, 3
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-asynciteratorprototype]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-asynciteratorprototype)

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

`@@asyncIterator`

63

79

57

50

11.1

63

57

46

11.3

8.0

63

1.0

10.0.0

`AsyncIterator`

63

79

57

50

11.1

63

57

46

11.3

8.0

63

1.0

10.0.0


See also 
--------


-   [`async function*`](../statements/async_function*)
-   [Iteration protocols](../iteration_protocols)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncIterator>

