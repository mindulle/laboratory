Promise.prototype.finally()
===========================

 
The `finally()` method of [`Promise`](../promise) instances schedules a
function to be called when the promise is settled (either fulfilled or
rejected). It immediately returns an equivalent [`Promise`](../promise)
object, allowing you to
[chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises#chaining)
calls to other promise methods.

This lets you avoid duplicating code in both the promise\'s
[`then()`](then) and [`catch()`](catch) handlers.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
promiseInstance.finally(onFinally)
```




 
### Parameters

 

[`onFinally`](#onfinally)

:   A function to asynchronously execute when this promise becomes
    settled. Its return value is ignored unless the returned value is a
    rejected promise. The function is called with no arguments.



 
### Return value 

 
Returns an equivalent [`Promise`](../promise). If the handler throws an
error or returns a rejected promise, the promise returned by `finally()`
will be rejected with that value instead. Otherwise, the return value of
the handler does not affect the state of the original promise.



 
Description
-----------

 
The `finally()` method can be useful if you want to do some processing
or cleanup once the promise is settled, regardless of its outcome.

The `finally()` method is very similar to calling
[`then(onFinally, onFinally)`](then). However, there are a couple of
differences:

-   When creating a function inline, you can pass it once, instead of
    being forced to either declare it twice, or create a variable for
    it.
-   The `onFinally` callback does not receive any argument. This use
    case is for precisely when you *do not care* about the rejection
    reason or the fulfillment value, and so there\'s no need to provide
    it.
-   A `finally()` call is usually transparent and does not change the
    eventual state of the original promise. So for example:
    -   Unlike `Promise.resolve(2).then(() => 77, () => {})`, which
        returns a promise eventually fulfilled with the value `77`,
        `Promise.resolve(2).finally(() => 77)` returns a promise
        eventually fulfilled with the value `2`.
    -   Similarly, unlike `Promise.reject(3).then(() => {}, () => 88)`,
        which returns a promise eventually fulfilled with the value
        `88`, `Promise.reject(3).finally(() => 88)` returns a promise
        eventually rejected with the reason `3`.

 
**Note:** A `throw` (or returning a rejected promise) in the `finally`
callback still rejects the returned promise. For example, both
`Promise.reject(3).finally(() => { throw 99; })` and
`Promise.reject(3).finally(() => Promise.reject(99))` reject the
returned promise with the reason `99`.


Like [`catch()`](catch), `finally()` internally calls the `then` method
on the object upon which it was called. If `onFinally` is not a
function, `then()` is called with `onFinally` as both arguments ---
which, for [`Promise.prototype.then()`](then), means that no useful
handler is attached. Otherwise, `then()` is called with two internally
created functions, which behave like the following:

 
**Warning:** This is only for demonstration purposes and is not a
polyfill.


 
 
[js]


```js
promise.then(
  (value) => Promise.resolve(onFinally()).then(() => value),
  (reason) =>
    Promise.resolve(onFinally()).then(() => {
      throw reason;
    }),
);
```


Because `finally()` calls `then()`, it supports subclassing. Moreover,
notice the [`Promise.resolve()`](resolve) call above --- in reality,
`onFinally()`\'s return value is resolved using the same algorithm as
`Promise.resolve()`, but the actual constructor used to construct the
resolved promise will be the subclass. `finally()` gets this constructor
through [`promise.constructor[@@species]`](@@species).



 
Examples
--------


 
### Using finally() 

 
 
 
[js]


```js
let isLoading = true;

fetch(myRequest)
  .then((response) => {
    const contentType = response.headers.get("content-type");
    if (contentType && contentType.includes("application/json")) {
      return response.json();
    }
    throw new TypeError("Oops, we haven't got JSON!");
  })
  .then((json) => {
    /* process your JSON further */
  })
  .catch((error) => {
    console.error(error); // this line can also throw, e.g. when console = {}
  })
  .finally(() => {
    isLoading = false;
  });
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-promise.prototype.finally]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-promise.prototype.finally)

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

`finally`

63

18

58

50

11.1

63

58

46

11.3

8.0

63

1.0

10.0.0

 
See also 
--------

 
-   [Polyfill of `Promise.prototype.finally` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-promise)
-   [`Promise`](../promise)
-   [`Promise.prototype.then()`](then)
-   [`Promise.prototype.catch()`](catch)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/finally>

