Symbol.asyncIterator
====================

 
The `Symbol.asyncIterator` static data property represents the
[well-known symbol](../symbol#well-known_symbols) `@@asyncIterator`. The
[async iterable
protocol](../../iteration_protocols#the_async_iterator_and_async_iterable_protocols)
looks up this symbol for the method that returns the async iterator for
an object. In order for an object to be async iterable, it must have an
`@@asyncIterator` key.


 
Try it 
------

 



 
Value
-----

 
The well-known symbol `@@asyncIterator`.

 
Property attributes of `Symbol.asyncIterator`




Writable

no

Enumerable

no

Configurable

no

 
Examples
--------


 
### User-defined async iterables 

 
You can define your own async iterable by setting the
`[Symbol.asyncIterator]` property on an object.

 
 
[js]


```js
const myAsyncIterable = {
  async *[Symbol.asyncIterator]() {
    yield "hello";
    yield "async";
    yield "iteration!";
  },
};

(async () => {
  for await (const x of myAsyncIterable) {
    console.log(x);
  }
})();
// Logs:
// "hello"
// "async"
// "iteration!"
```


When creating an API, remember that async iterables are designed to
represent something *iterable* --- like a stream of data or a list ---,
not to completely replace callbacks and events in most situations.



 
### Built-in async iterables 

 
There is no object in the core JavaScript language that is async
iterable. Some web APIs, such as
[`ReadableStream`](https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream),
have the `Symbol.asyncIterator` method set by default.



Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.asynciterator]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.asynciterator)

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

`asyncIterator`

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

 
-   [Iteration protocols](../../iteration_protocols)
-   [for await\...of](../../statements/for-await...of)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/asyncIterator>

