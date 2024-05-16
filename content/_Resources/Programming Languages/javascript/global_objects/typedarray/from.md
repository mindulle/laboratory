TypedArray.from()
=================

 
The `TypedArray.from()` static method creates a new [typed
array](../typedarray#typedarray_objects) from an array-like or iterable
object. This method is nearly the same as
[`Array.from()`](../array/from).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
TypedArray.from(arrayLike, mapFn)
TypedArray.from(arrayLike, mapFn, thisArg)
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

 

[`arrayLike`](#arraylike)

:   An iterable or array-like object to convert to a typed array.

[`mapFn`](#mapfn) [Optional]

:   A function to call on every element of the typed array. If provided,
    every value to be added to the array is first passed through this
    function, and `mapFn`\'s return value is added to the typed array
    instead. The function is called with the following arguments:

    [`element`](#element)

    :   The current element being processed in the typed array.

    [`index`](#index)

    :   The index of the current element being processed in the typed
        array.

[`thisArg`](#thisarg) [Optional]

:   Value to use as `this` when executing `mapFn`.



 
### Return value 

 
A new [`TypedArray`](../typedarray) instance.



 
Description
-----------

 
See [`Array.from()`](../array/from) for more details.

There are some subtle distinctions between
[`Array.from()`](../array/from) and `TypedArray.from()` (note: the
`this` value mentioned below is the `this` value that
`TypedArray.from()` was called with, not the `thisArg` argument used to
invoke `mapFn`):

-   If the `this` value of `TypedArray.from()` is not a constructor,
    `TypedArray.from()` will throw a [`TypeError`](../typeerror), while
    `Array.from()` defaults to creating a new [`Array`](../array).
-   The object constructed by `this` must be a `TypedArray` instance,
    while `Array.from()` allows its `this` value to be constructed to
    any object.
-   When the `source` parameter is an iterator, `TypedArray.from()`
    first collects all the values from the iterator, then creates an
    instance of `this` using the count, and finally sets the values on
    the instance. `Array.from()` sets each value as it receives them
    from the iterator, then sets its `length` at the end.
-   `TypedArray.from()` uses `[[Set]]` while `Array.from()` uses
    `[[DefineOwnProperty]]`. Hence, when working with
    [`Proxy`](../proxy) objects, it calls
    [`handler.set()`](../proxy/proxy/set) to create new elements rather
    than [`handler.defineProperty()`](../proxy/proxy/defineproperty).
-   When `Array.from()` gets an array-like which isn\'t an iterator, it
    respects holes. `TypedArray.from()` will ensure the result is dense.



 
Examples
--------


 
### From an iterable object (Set) 

 
 
 
[js]


```js
const s = new Set([1, 2, 3]);
Uint8Array.from(s);
// Uint8Array [ 1, 2, 3 ]
```




 
### From a string 

 
 
 
[js]


```js
Int16Array.from("123");
// Int16Array [ 1, 2, 3 ]
```




 
### Use with arrow function and map 

 
Using an arrow function as the map function to manipulate the elements

 
 
[js]


```js
Float32Array.from([1, 2, 3], (x) => x + x);
// Float32Array [ 2, 4, 6 ]
```




 
### Generate a sequence of numbers 

 
 
 
[js]


```js
Uint8Array.from({ length: 5 }, (v, k) => k);
// Uint8Array [ 0, 1, 2, 3, 4 ]
```




 
### Calling from() on non-TypedArray constructors 

 
The `this` value of `from()` must be a constructor that returns a
`TypedArray` instance.

 
 
[js]


```js
function NotArray(len) {
  console.log("NotArray called with length", len);
}

Int8Array.from.call({}, []); // TypeError: #<Object> is not a constructor
Int8Array.from.call(NotArray, []);
// NotArray called with length 0
// TypeError: Method %TypedArray%.from called on incompatible receiver #<NotArray>
```


 
 
[js]


```js
function NotArray2(len) {
  console.log("NotArray2 called with length", len);
  return new Uint8Array(len);
}
console.log(Int8Array.from.call(NotArray2, [1, 2, 3]));
// NotArray2 called with length 3
// Uint8Array(3) [ 1, 2, 3 ]
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.from]](#)

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

`from`

45

12

38

32

10

45

38

32

10

5.0

45

1.0

4.0.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.from` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.of()`](of)
-   [`TypedArray.prototype.map()`](map)
-   [`Array.from()`](../array/from)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/from>

