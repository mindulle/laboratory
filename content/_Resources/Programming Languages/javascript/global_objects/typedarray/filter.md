TypedArray.prototype.filter()
=============================

 
The `filter()` method of [`TypedArray`](../typedarray) instances creates
a copy of a portion of a given typed array, filtered down to just the
elements from the given typed array that pass the test implemented by
the provided function. This method has the same algorithm as
[`Array.prototype.filter()`](../array/filter).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
filter(callbackFn)
filter(callbackFn, thisArg)
```




 
### Parameters

 

[`callbackFn`](#callbackfn)

:   A function to execute for each element in the typed array. It should
    return a
    [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
    value to keep the element in the resulting typed array, and a
    [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
    value otherwise. The function is called with the following
    arguments:

    [`element`](#element)

    :   The current element being processed in the typed array.

    [`index`](#index)

    :   The index of the current element being processed in the typed
        array.

    [`array`](#array)

    :   The typed array `filter()` was called upon.

[`thisArg`](#thisarg) [Optional]

:   A value to use as `this` when executing `callbackFn`. See [iterative
    methods](../array#iterative_methods).



 
### Return value 

 
A copy of the given typed array containing just the elements that pass
the test. If no elements pass the test, an empty typed array is
returned.



 
Description
-----------

 
See [`Array.prototype.filter()`](../array/filter) for more details. This
method is not generic and can only be called on typed array instances.



 
Examples
--------


 
### Filtering out all small values 

 
The following example uses `filter()` to create a filtered typed array
that has all elements with values less than 10 removed.

 
 
[js]


```js
function isBigEnough(element, index, array) {
  return element >= 10;
}
new Uint8Array([12, 5, 8, 130, 44]).filter(isBigEnough);
// Uint8Array [ 12, 130, 44 ]
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.filter]](#)

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

`filter`

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

 
-   [Polyfill of `TypedArray.prototype.filter` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.forEach()`](foreach)
-   [`TypedArray.prototype.every()`](every)
-   [`TypedArray.prototype.map()`](map)
-   [`TypedArray.prototype.some()`](some)
-   [`TypedArray.prototype.reduce()`](reduce)
-   [`Array.prototype.filter()`](../array/filter)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/filter>

