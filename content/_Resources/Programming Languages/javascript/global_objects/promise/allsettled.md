Promise.allSettled()
====================

 
The `Promise.allSettled()` static method takes an iterable of promises
as input and returns a single [`Promise`](../promise). This returned
promise fulfills when all of the input\'s promises settle (including
when an empty iterable is passed), with an array of objects that
describe the outcome of each promise.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Promise.allSettled(iterable)
```




 
### Parameters

 

[`iterable`](#iterable)

:   An [iterable](../../iteration_protocols#the_iterable_protocol) (such
    as an [`Array`](../array)) of promises.



 
### Return value 

 
A [`Promise`](../promise) that is:

-   **Already fulfilled**, if the `iterable` passed is empty.
-   **Asynchronously fulfilled**, when all promises in the given
    `iterable` have settled (either fulfilled or rejected). The
    fulfillment value is an array of objects, each describing the
    outcome of one promise in the `iterable`, in the order of the
    promises passed, regardless of completion order. Each outcome object
    has the following properties:

    [`status`](#status)

    :   A string, either `"fulfilled"` or `"rejected"`, indicating the
        eventual state of the promise.

    [`value`](#value)

    :   Only present if `status` is `"fulfilled"`. The value that the
        promise was fulfilled with.

    [`reason`](#reason)

    :   Only present if `status` is `"rejected"`. The reason that the
        promise was rejected with.

    If the `iterable` passed is non-empty but contains no pending
    promises, the returned promise is still asynchronously (instead of
    synchronously) fulfilled.



 
Description
-----------

 
The `Promise.allSettled()` method is one of the [promise
concurrency](../promise#promise_concurrency) methods.
`Promise.allSettled()` is typically used when you have multiple
asynchronous tasks that are not dependent on one another to complete
successfully, or you\'d always like to know the result of each promise.

In comparison, the Promise returned by [`Promise.all()`](all) may be
more appropriate if the tasks are dependent on each other, or if you\'d
like to immediately reject upon any of them rejecting.



 
Examples
--------


 
### Using Promise.allSettled() 

 
 
 
[js]


```js
Promise.allSettled([
  Promise.resolve(33),
  new Promise((resolve) => setTimeout(() => resolve(66), 0)),
  99,
  Promise.reject(new Error("an error")),
]).then((values) => console.log(values));

// [
//   { status: 'fulfilled', value: 33 },
//   { status: 'fulfilled', value: 66 },
//   { status: 'fulfilled', value: 99 },
//   { status: 'rejected', reason: Error: an error }
// ]
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-promise.allsettled]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-promise.allsettled)

  -----------------------------------------------------------------------------------------------------------------------------


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

`allSettled`

76

79

71

63

13

76

79

54

13

12.0

76

1.0

12.9.0

 
See also 
--------

 
-   [Polyfill of `Promise.allSettled` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-promise)
-   [Using
    promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)
    guide
-   [Graceful asynchronous programming with
    promises](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Promises)
-   [`Promise`](../promise)
-   [`Promise.all()`](all)
-   [`Promise.any()`](any)
-   [`Promise.race()`](race)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/allSettled>

