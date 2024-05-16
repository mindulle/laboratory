Atomics.notify()
================


The `Atomics.notify()` static method notifies up some agents that are
sleeping in the wait queue.

 
**Note:** This operation only works with an
[`Int32Array`](../int32array) or [`BigInt64Array`](../bigint64array)
that views a [`SharedArrayBuffer`](../sharedarraybuffer). It will return
`0` on non-shared `ArrayBuffer` objects.




Syntax
------




[js]


```js
Atomics.notify(typedArray, index, count)
```





### Parameters



[`typedArray`](#typedarray)

:   An [`Int32Array`](../int32array) or
    [`BigInt64Array`](../bigint64array) that views a
    [`SharedArrayBuffer`](../sharedarraybuffer).

[`index`](#index)

:   The position in the `typedArray` to wake up on.

[`count`](#count) [Optional]

:   The number of sleeping agents to notify. Defaults to
    [`Infinity`](../infinity).




### Return value 


-   Returns the number of woken up agents.
-   Returns `0`, if a non-shared [`ArrayBuffer`](../arraybuffer) object
    is used.




### Exceptions



[`TypeError`](../typeerror)

:   Thrown if `typedArray` is not an [`Int32Array`](../int32array) or
    [`BigInt64Array`](../bigint64array) that views a
    [`SharedArrayBuffer`](../sharedarraybuffer).

[`RangeError`](../rangeerror)

:   Thrown if `index` is out of bounds in the `typedArray`.




Examples
--------



### Using `notify` 


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


  ---------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-atomics.notify]](https://tc39.es/ecma262/multipage/structured-data.html#sec-atomics.notify)

  ---------------------------------------------------------------------------------------------------------


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

`notify`

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
-   [`Atomics.wait()`](wait)
-   [`Atomics.waitAsync()`](waitasync)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Atomics/notify>

