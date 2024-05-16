TypedArray.prototype.reduce()
=============================

 
The `reduce()` method of [`TypedArray`](../typedarray) instances
executes a user-supplied \"reducer\" callback function on each element
of the typed array, in order, passing in the return value from the
calculation on the preceding element. The final result of running the
reducer across all elements of the typed array is a single value. This
method has the same algorithm as
[`Array.prototype.reduce()`](../array/reduce).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
reduce(callbackFn)
reduce(callbackFn, initialValue)
```




 
### Parameters

 

[`callbackFn`](#callbackfn)

:   A function to execute for each element in the typed array. Its
    return value becomes the value of the `accumulator` parameter on the
    next invocation of `callbackFn`. For the last invocation, the return
    value becomes the return value of `reduce()`. The function is called
    with the following arguments:

    [`accumulator`](#accumulator)

    :   The value resulting from the previous call to `callbackFn`. On
        the first call, its value is `initialValue` if the latter is
        specified; otherwise its value is `array[0]`.

    [`currentValue`](#currentvalue)

    :   The value of the current element. On the first call, its value
        is `array[0]` if `initialValue` is specified; otherwise its
        value is `array[1]`.

    [`currentIndex`](#currentindex)

    :   The index position of `currentValue` in the typed array. On the
        first call, its value is `0` if `initialValue` is specified,
        otherwise `1`.

    [`array`](#array)

    :   The typed array `reduce()` was called upon.

[`initialValue`](#initialvalue) [Optional]

:   A value to which `accumulator` is initialized the first time the
    callback is called. If `initialValue` is specified, `callbackFn`
    starts executing with the first value in the typed array as
    `currentValue`. If `initialValue` is *not* specified, `accumulator`
    is initialized to the first value in the typed array, and
    `callbackFn` starts executing with the second value in the typed
    array as `currentValue`. In this case, if the typed array is empty
    (so that there\'s no first value to return as `accumulator`), an
    error is thrown.



 
### Return value 

 
The value that results from running the \"reducer\" callback function to
completion over the entire typed array.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if the typed array contains no elements and `initialValue` is
    not provided.



 
Description
-----------

 
See [`Array.prototype.reduce()`](../array/reduce) for more details. This
method is not generic and can only be called on typed array instances.



 
Examples
--------


 
### Sum up all values within an array 

 
 
 
[js]


```js
const total = new Uint8Array([0, 1, 2, 3]).reduce((a, b) => a + b);
// total === 6
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.reduce]](#)

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

`reduce`

45

12

37

32

10

45

37

32

10

5.0

45

1.0

4.0.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.reduce` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.map()`](map)
-   [`TypedArray.prototype.reduceRight()`](reduceright)
-   [`Array.prototype.reduce()`](../array/reduce)
-   [`Object.groupBy()`](../object/groupby)
-   [`Map.groupBy()`](../map/groupby)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/reduce>

