TypedArray.prototype.forEach()
==============================

 
The `forEach()` method of [`TypedArray`](../typedarray) instances
executes a provided function once for each typed array element. This
method has the same algorithm as
[`Array.prototype.forEach()`](../array/foreach).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
forEach(callbackFn)
forEach(callbackFn, thisArg)
```




 
### Parameters

 

[`callbackFn`](#callbackfn)

:   A function to execute for each element in the typed array. Its
    return value is discarded. The function is called with the following
    arguments:

    [`element`](#element)

    :   The current element being processed in the typed array.

    [`index`](#index)

    :   The index of the current element being processed in the typed
        array.

    [`array`](#array)

    :   The typed array `forEach()` was called upon.

[`thisArg`](#thisarg) [Optional]

:   A value to use as `this` when executing `callbackFn`. See [iterative
    methods](../array#iterative_methods).



 
### Return value 

 
None ([`undefined`](../undefined)).



 
Description
-----------

 
See [`Array.prototype.forEach()`](../array/foreach) for more details.
This method is not generic and can only be called on typed array
instances.



 
Examples
--------


 
### Logging the contents of a typed array 

 
The following code logs a line for each element in a typed array:

 
 
[js]


```js
function logArrayElements(element, index, array) {
  console.log(`a[${index}] = ${element}`);
}

new Uint8Array([0, 1, 2, 3]).forEach(logArrayElements);
// Logs:
// a[0] = 0
// a[1] = 1
// a[2] = 2
// a[3] = 3
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.foreach]](#)

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

`forEach`

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

 
-   [Polyfill of `TypedArray.prototype.forEach` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.find()`](find)
-   [`TypedArray.prototype.map()`](map)
-   [`TypedArray.prototype.filter()`](filter)
-   [`TypedArray.prototype.every()`](every)
-   [`TypedArray.prototype.some()`](some)
-   [`Array.prototype.forEach()`](../array/foreach)
-   [`Map.prototype.forEach()`](../map/foreach)
-   [`Set.prototype.forEach()`](../set/foreach)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/forEach>

