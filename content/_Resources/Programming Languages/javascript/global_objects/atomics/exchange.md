Atomics.exchange()
==================


The `Atomics.exchange()` static method exchanges a given value at a
given position in the array and returns the old value at that position.
This atomic operation guarantees that no other write happens between the
read of the old value and the write of the new value.



Try it 
------






Syntax
------




[js]


```js
Atomics.exchange(typedArray, index, value)
```





### Parameters



[`typedArray`](#typedarray)

:   An integer typed array. One of [`Int8Array`](../int8array),
    [`Uint8Array`](../uint8array), [`Int16Array`](../int16array),
    [`Uint16Array`](../uint16array), [`Int32Array`](../int32array),
    [`Uint32Array`](../uint32array),
    [`BigInt64Array`](../bigint64array), or
    [`BigUint64Array`](../biguint64array).

[`index`](#index)

:   The position in the `typedArray` to exchange a `value`.

[`value`](#value)

:   The number to exchange.




### Return value 


The old value at the given position (`typedArray[index]`).




### Exceptions



[`TypeError`](../typeerror)

:   Thrown if `typedArray` is not one of the allowed integer types.

[`RangeError`](../rangeerror)

:   Thrown if `index` is out of bounds in the `typedArray`.




Examples
--------



### Using exchange() 




[js]


```js
const sab = new SharedArrayBuffer(1024);
const ta = new Uint8Array(sab);

Atomics.exchange(ta, 0, 12); // returns 0, the old value
Atomics.load(ta, 0); // 12
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-atomics.exchange]](https://tc39.es/ecma262/multipage/structured-data.html#sec-atomics.exchange)

  -------------------------------------------------------------------------------------------------------------


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

`exchange`

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
-   [`Atomics.compareExchange()`](compareexchange)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Atomics/exchange>

