Atomics.or()
============


The `Atomics.or()` static method computes a bitwise OR with a given
value at a given position in the array, and returns the old value at
that position. This atomic operation guarantees that no other write
happens until the modified value is written back.



Try it 
------






Syntax
------




[js]


```js
Atomics.or(typedArray, index, value)
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

:   The position in the `typedArray` to compute the bitwise OR.

[`value`](#value)

:   The number to compute the bitwise OR with.




### Return value 


The old value at the given position (`typedArray[index]`).




### Exceptions



[`TypeError`](../typeerror)

:   Thrown if `typedArray` is not one of the allowed integer types.

[`RangeError`](../rangeerror)

:   Thrown if `index` is out of bounds in the `typedArray`.




Description
-----------


The bitwise OR operation yields 1, if either `a` or `b` are 1. The truth
table for the OR operation is:


  `a`   `b`   `a | b`
  ----- ----- ---------
  0     0     0
  0     1     1
  1     0     1
  1     1     1


For example, a bitwise OR of `5 | 1` results in `0101` which is 5 in
decimal.

```text
5  0101
1  0001
   ----
5  0101
```




Examples
--------



### Using or 




[js]


```js
const sab = new SharedArrayBuffer(1024);
const ta = new Uint8Array(sab);
ta[0] = 2;

Atomics.or(ta, 0, 1); // returns 2, the old value
Atomics.load(ta, 0); // 3
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-atomics.or]](https://tc39.es/ecma262/multipage/structured-data.html#sec-atomics.or)

  -------------------------------------------------------------------------------------------------


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

`or`

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
-   [`Atomics.and()`](and)
-   [`Atomics.xor()`](xor)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Atomics/or>

