Atomics.waitAsync()
===================


The `Atomics.waitAsync()` static method waits asynchronously on a shared
memory location and returns a [`Promise`](../promise).

Unlike [`Atomics.wait()`](wait), `waitAsync` is non-blocking and usable
on the main thread.

 
**Note:** This operation only works with an
[`Int32Array`](../int32array) or [`BigInt64Array`](../bigint64array)
that views a [`SharedArrayBuffer`](../sharedarraybuffer).




Syntax
------




[js]


```js
Atomics.waitAsync(typedArray, index, value)
Atomics.waitAsync(typedArray, index, value, timeout)
```





### Parameters



[`typedArray`](#typedarray)

:   An [`Int32Array`](../int32array) or
    [`BigInt64Array`](../bigint64array) that views a
    [`SharedArrayBuffer`](../sharedarraybuffer).

[`index`](#index)

:   The position in the `typedArray` to wait on.

[`value`](#value)

:   The expected value to test.

[`timeout`](#timeout) [Optional]

:   Time to wait in milliseconds. [`NaN`](../nan) (and values that get
    converted to `NaN`, such as `undefined`) becomes
    [`Infinity`](../infinity). Negative values become `0`.




### Return value 


An [`Object`](../object) with the following properties:

[`async`](#async)

:   A boolean indicating whether the `value` property is a
    [`Promise`](../promise) or not.

[`value`](#value_2)

:   If `async` is `false`, it will be a string which is either
    `"not-equal"` or `"timed-out"` (only when the `timeout` parameter is
    `0`). If `async` is `true`, it will be a [`Promise`](../promise)
    which is fulfilled with a string value, either `"ok"` or
    `"timed-out"`. The promise is never rejected.




### Exceptions



[`TypeError`](../typeerror)

:   Thrown if `typedArray` is not an [`Int32Array`](../int32array) or
    [`BigInt64Array`](../bigint64array) that views a
    [`SharedArrayBuffer`](../sharedarraybuffer).

[`RangeError`](../rangeerror)

:   Thrown if `index` is out of bounds in the `typedArray`.




Examples
--------



### Using waitAsync() 


Given a shared `Int32Array`.



[js]


```js
const sab = new SharedArrayBuffer(1024);
const int32 = new Int32Array(sab);
```


A reading thread is sleeping and waiting on location 0 which is expected
to be 0. The `result.value` will be a promise.



[js]


```js
const result = Atomics.waitAsync(int32, 0, 0, 1000);
// { async: true, value: Promise {<pending>} }
```


In the reading thread or in another thread, the memory location 0 is
called and the promise can be resolved with `"ok"`.



[js]


```js
Atomics.notify(int32, 0);
// { async: true, value: Promise {<fulfilled>: 'ok'} }
```


If it isn\'t resolving to `"ok"`, the value in the shared memory
location wasn\'t the expected (the `value` would be `"not-equal"`
instead of a promise) or the timeout was reached (the promise will
resolve to `"time-out"`).



Specifications
--------------


  ---------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-atomics.waitasync]](https://tc39.es/ecma262/multipage/structured-data.html#sec-atomics.waitasync)

  ---------------------------------------------------------------------------------------------------------------


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

`waitAsync`

87

87

No

75

16.4

89

No

63

16.4

15.0

89

1.4

16.0.0


See also 
--------


-   [`Atomics`](../atomics)
-   [`Atomics.wait()`](wait)
-   [`Atomics.notify()`](notify)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Atomics/waitAsync>

