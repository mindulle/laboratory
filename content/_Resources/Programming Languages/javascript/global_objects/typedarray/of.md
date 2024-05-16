TypedArray.of()
===============

 
The `TypedArray.of()` static method creates a new [typed
array](../typedarray#typedarray_objects) from a variable number of
arguments. This method is nearly the same as
[`Array.of()`](../array/of).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
TypedArray.of()
TypedArray.of(element1)
TypedArray.of(element1, element2)
TypedArray.of(element1, element2, /* …, */ elementN)
```


Where `TypedArray` is one of:

-   [`Int8Array`](../int8array)
-   [`Uint8Array`](../uint8array)
-   [`Uint8ClampedArray`](../uint8clampedarray)
-   [`Int16Array`](../int16array)
-   [`Uint16Array`](../uint16array)
-   [`Int32Array`](../int32array)
-   [`Uint32Array`](../uint32array)
-   [`Float32Array`](../float32array)
-   [`Float64Array`](../float64array)
-   [`BigInt64Array`](../bigint64array)
-   [`BigUint64Array`](../biguint64array)



 
### Parameters

 

[`element1`](#element1), ..., `elementN`

:   Elements used to create the typed array.



 
### Return value 

 
A new [`TypedArray`](../typedarray) instance.



 
Description
-----------

 
See [`Array.of()`](../array/of) for more details. There are some subtle
distinctions between [`Array.of()`](../array/of) and `TypedArray.of()`:

-   If the `this` value passed to `TypedArray.of()` is not a
    constructor, `TypedArray.from()` will throw a
    [`TypeError`](../typeerror), while `Array.of()` defaults to creating
    a new [`Array`](../array).
-   `TypedArray.of()` uses `[[Set]]` while `Array.of()` uses
    `[[DefineOwnProperty]]`. Hence, when working with
    [`Proxy`](../proxy) objects, it calls
    [`handler.set()`](../proxy/proxy/set) to create new elements rather
    than [`handler.defineProperty()`](../proxy/proxy/defineproperty).



 
Examples
--------


 
### Using of() 

 
 
 
[js]


```js
Uint8Array.of(1); // Uint8Array [ 1 ]
Int8Array.of("1", "2", "3"); // Int8Array [ 1, 2, 3 ]
Float32Array.of(1, 2, 3); // Float32Array [ 1, 2, 3 ]
Int16Array.of(undefined); // Int16Array [ 0 ]
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.of]](#)

  -----------------------------------------------------------------------


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

`of`

45

12

38

32

9.1

45

38

32

9.3

5.0

45

1.0

4.0.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.of` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.from()`](from)
-   [`Array.of()`](../array/of)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/of>

