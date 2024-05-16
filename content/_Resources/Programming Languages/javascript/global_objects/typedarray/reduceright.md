TypedArray.prototype.reduceRight()
==================================

 
The `reduceRight()` method of [`TypedArray`](../typedarray) instances
applies a function against an accumulator and each value of the typed
array (from right-to-left) to reduce it to a single value. This method
has the same algorithm as
[`Array.prototype.reduceRight()`](../array/reduceright).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
reduceRight(callbackFn)
reduceRight(callbackFn, initialValue)
```




 
### Parameters

 

[`callbackFn`](#callbackfn)

:   A function to execute for each element in the typed array. Its
    return value becomes the value of the `accumulator` parameter on the
    next invocation of `callbackFn`. For the last invocation, the return
    value becomes the return value of `reduceRight()`. The function is
    called with the following arguments:

    [`accumulator`](#accumulator)

    :   The value resulting from the previous call to `callbackFn`. On
        the first call, its value is `initialValue` if the latter is
        specified; otherwise its value is the last element of the typed
        array.

    [`currentValue`](#currentvalue)

    :   The value of the current element. On the first call, its value
        is the last element if `initialValue` is specified; otherwise
        its value is the second-to-last element.

    [`currentIndex`](#currentindex)

    :   The index position of `currentValue` in the typed array. On the
        first call, its value is `array.length - 1` if `initialValue` is
        specified, otherwise `array.length - 2`.

    [`array`](#array)

    :   The typed array `reduceRight()` was called upon.

[`initialValue`](#initialvalue) [Optional]

:   Value to use as accumulator to the first call of the `callbackFn`.
    If no initial value is supplied, the last element in the typed array
    will be used and skipped. Calling `reduceRight()` on an empty typed
    array without an initial value creates a `TypeError`.



 
### Return value 

 
The value that results from the reduction.



 
Description
-----------

 
See [`Array.prototype.reduceRight()`](../array/reduceright) for more
details. This method is not generic and can only be called on typed
array instances.



 
Examples
--------


 
### Sum up all values within an array 

 
 
 
[js]


```js
const total = new Uint8Array([0, 1, 2, 3]).reduceRight((a, b) => a + b);
// total === 6
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.reduceright]](#)

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

`reduceRight`

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

 
-   [Polyfill of `TypedArray.prototype.reduceRight` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.map()`](map)
-   [`TypedArray.prototype.reduce()`](reduce)
-   [`Array.prototype.reduceRight()`](../array/reduceright)
-   [`Object.groupBy()`](../object/groupby)
-   [`Map.groupBy()`](../map/groupby)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/reduceRight>

