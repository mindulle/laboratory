TypedArray.prototype.map()
==========================

 
The `map()` method of [`TypedArray`](../typedarray) instances creates a
new typed array populated with the results of calling a provided
function on every element in the calling typed array. This method has
the same algorithm as [`Array.prototype.map()`](../array/map).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
map(callbackFn)
map(callbackFn, thisArg)
```




 
### Parameters

 

[`callbackFn`](#callbackfn)

:   A function to execute for each element in the typed array. Its
    return value is added as a single element in the new typed array.
    The function is called with the following arguments:

    [`element`](#element)

    :   The current element being processed in the typed array.

    [`index`](#index)

    :   The index of the current element being processed in the typed
        array.

    [`array`](#array)

    :   The typed array `map()` was called upon.

[`thisArg`](#thisarg) [Optional]

:   A value to use as `this` when executing `callbackFn`. See [iterative
    methods](../array#iterative_methods).



 
### Return value 

 
A new typed array with each element being the result of the callback
function.



 
Description
-----------

 
See [`Array.prototype.map()`](../array/map) for more details. This
method is not generic and can only be called on typed array instances.



 
Examples
--------


 
### Mapping a typed array to a typed array of square roots 

 
The following code takes a typed array and creates a new typed array
containing the square roots of the numbers in the first typed array.

 
 
[js]


```js
const numbers = new Uint8Array([1, 4, 9]);
const roots = numbers.map(Math.sqrt);
// roots is now: Uint8Array [1, 2, 3],
// numbers is still Uint8Array [1, 4, 9]
```




 
### Mapping a typed array of numbers using a function containing an argument 

 
The following code shows how `map()` works when a function requiring one
argument is used with it. The argument will automatically be assigned to
each element of the typed array as `map()` loops through the original
typed array.

 
 
[js]


```js
const numbers = new Uint8Array([1, 4, 9]);
const doubles = numbers.map((num) => num * 2);
// doubles is now Uint8Array [2, 8, 18]
// numbers is still Uint8Array [1, 4, 9]
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.map]](#)

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

`map`

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

 
-   [Polyfill of `TypedArray.prototype.map` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.forEach()`](foreach)
-   [`TypedArray.from()`](from)
-   [`Array.prototype.map()`](../array/map)
-   [`Map`](../map)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/map>

