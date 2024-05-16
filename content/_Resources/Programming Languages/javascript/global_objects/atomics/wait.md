Atomics.wait()
==============


The `Atomics.wait()` static method verifies that a shared memory
location still contains a given value and if so sleeps, awaiting a
wake-up notification or times out. It returns a string which is either
`"ok"`, `"not-equal"`, or `"timed-out"`.

 
**Note:** This operation only works with an
[`Int32Array`](../int32array) or [`BigInt64Array`](../bigint64array)
that views a [`SharedArrayBuffer`](../sharedarraybuffer), and may not be
allowed on the main thread. For a non-blocking, asynchronous version of
this method, see [`Atomics.waitAsync()`](waitasync).




Syntax
------




[js]


```js
Atomics.wait(typedArray, index, value)
Atomics.wait(typedArray, index, value, timeout)
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


A string which is either `"ok"`, `"not-equal"`, or `"timed-out"`.




### Exceptions



[`TypeError`](../typeerror)

:   Thrown in one of the following cases:

    -   If `typedArray` is not an [`Int32Array`](../int32array) or
        [`BigInt64Array`](../bigint64array) that views a
        [`SharedArrayBuffer`](../sharedarraybuffer).
    -   If the current thread cannot be blocked (for example, because
        it\'s the main thread).

[`RangeError`](../rangeerror)

:   Thrown if `index` is out of bounds in the `typedArray`.




Examples
--------



### Using wait() 


Given a shared `Int32Array`:



[js]


```js
const sab = new SharedArrayBuffer(1024);
const int32 = new Int32Array(sab);
```


A reading thread is sleeping and waiting on location 0 which is expected
to be 0. As long as that is true, it will not go on. However, once the
writing thread has stored a new value, it will be notified by the
writing thread and return the new value (123).



[js]


```js
Atomics.wait(int32, 0, 0);
console.log(int32[0]); // 123
```


A writing thread stores a new value and notifies the waiting thread once
it has written:



[js]


```js
console.log(int32[0]); // 0;
Atomics.store(int32, 0, 123);
Atomics.notify(int32, 0, 1);
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-atomics.wait]](https://tc39.es/ecma262/multipage/structured-data.html#sec-atomics.wait)

  -----------------------------------------------------------------------------------------------------


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

`wait`

68

79

78

55

15.2

89

79

63

15.2

15.0

89

1.0

8.10.0


See also 
--------


-   [`Atomics`](../atomics)
-   [`Atomics.waitAsync()`](waitasync)
-   [`Atomics.notify()`](notify)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Atomics/wait>

