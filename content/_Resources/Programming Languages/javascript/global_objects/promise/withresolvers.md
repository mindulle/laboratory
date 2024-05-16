Promise.withResolvers()
=======================

 
The `Promise.withResolvers()` static method returns an object containing
a new [`Promise`](../promise) object and two functions to resolve or
reject it, corresponding to the two parameters passed to the executor of
the [`Promise()`](promise) constructor.


 
Syntax
------

 
 
 
[js]


```js
Promise.withResolvers()
```




 
### Parameters

 
None.



 
### Return value 

 
A plain object containing the following properties:

[`promise`](#promise)

:   A [`Promise`](../promise) object.

[`resolve`](#resolve)

:   A function that resolves the promise. For its semantics, see the
    [`Promise()`](promise) constructor reference.

[`reject`](#reject)

:   A function that rejects the promise. For its semantics, see the
    [`Promise()`](promise) constructor reference.



 
Description
-----------

 
`Promise.withResolvers()` is exactly equivalent to the following code:

 
 
[js]


```js
let resolve, reject;
const promise = new Promise((res, rej) => {
  resolve = res;
  reject = rej;
});
```


Except that it is more concise and does not require the use of
[`let`](../../statements/let).

The key difference when using `Promise.withResolvers()` is that the
resolution and rejection functions now live in the same scope as the
promise itself, instead of being created and used once within the
executor. This may enable some more advanced use cases, such as when
reusing them for recurring events, particularly with streams and queues.
This also generally results in less nesting than wrapping a lot of logic
within the executor.

`Promise.withResolvers()` is generic and supports subclassing, which
means it can be called on subclasses of `Promise`, and the result will
contain a promise of the subclass type. To do so, the subclass\'s
constructor must implement the same signature as the
[`Promise()`](promise) constructor --- accepting a single `executor`
function that can be called with the `resolve` and `reject` callbacks as
parameters.



 
Examples
--------


 
### Transforming a stream to an async iterable 

 
The use case of `Promise.withResolvers()` is when you have a promise
that should be resolved or rejected by some event listener that cannot
be wrapped inside the promise executor. The following example transforms
a Node.js [readable
stream](https://nodejs.org/api/stream.html#class-streamreadable) to an
[async iterable](../../statements/async_function*). Each `promise` here
represents a single batch of data available, and each time the current
batch is read, a new promise is created for the next batch. Note how the
event listeners are only attached once, but actually call a different
version of the `resolve` and `reject` functions each time.

 
 
[js]


```js
async function* readableToAsyncIterable(stream) {
  let { promise, resolve, reject } = Promise.withResolvers();
  stream.on("error", (error) => reject(error));
  stream.on("end", () => resolve());
  stream.on("readable", () => resolve());

  while (stream.readable) {
    await promise;
    let chunk;
    while ((chunk = stream.read())) {
      yield chunk;
    }
    ({ promise, resolve, reject } = Promise.withResolvers());
  }
}
```




 
### Calling withResolvers() on a non-Promise constructor 

 
`Promise.withResolvers()` is a generic method. It can be called on any
constructor that implements the same signature as the `Promise()`
constructor. For example, we can call it on a constructor that passes
`console.log` as the `resolve` and `reject` functions to `executor`:

 
 
[js]


```js
class NotPromise {
  constructor(executor) {
    // The "resolve" and "reject" functions behave nothing like the native
    // promise's, but Promise.withResolvers() just returns them, as is.
    executor(
      (value) => console.log("Resolved", value),
      (reason) => console.log("Rejected", reason),
    );
  }
}

const { promise, resolve, reject } = Promise.withResolvers.call(NotPromise);
resolve("hello");
// Logs: Resolved hello
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------
  [ES Promise.withResolvers (2023)\
  [\#
  sec-promise.withResolvers]](https://tc39.es/proposal-promise-with-resolvers/#sec-promise.withResolvers)

  -----------------------------------------------------------------------------------------------------------------


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

`withResolvers`

119

119

121

105

preview

119

121

79

No

No

119

1.38

No

 
See also 
--------

 
-   [Polyfill of `Promise.withResolvers` in
    `core-js`](https://github.com/zloirock/core-js#promisewithresolvers)
-   [Using
    promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
    guide
-   [`Promise`](../promise)
-   [`Promise()` constructor](promise)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/withResolvers>

