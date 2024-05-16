TypedArray.prototype.toSorted()
===============================

 
The `toSorted()` method of [`TypedArray`](../typedarray) instances is
the [copying](../array#copying_methods_and_mutating_methods) version of
the [`sort()`](sort) method. It returns a new typed array with the
elements sorted in ascending order. This method has the same algorithm
as [`Array.prototype.toSorted()`](../array/tosorted), except that it
sorts the values numerically instead of as strings by default.


 
Syntax
------

 
 
 
[js]


```js
toSorted()
toSorted(compareFn)
```




 
### Parameters

 

[`compareFn`](#comparefn) [Optional]

:   Specifies a function that defines the sort order. If omitted, the
    typed array elements are sorted according to numeric value.

    [`a`](#a)

    :   The first element for comparison.

    [`b`](#b)

    :   The second element for comparison.



 
### Return value 

 
A new typed array with the elements sorted in ascending order.



 
Description
-----------

 
See [`Array.prototype.toSorted()`](../array/tosorted) for more details.
This method is not generic and can only be called on typed array
instances.



 
Examples
--------


 
### Sorting an array 

 
For more examples, see also the
[`Array.prototype.sort()`](../array/sort) method.

 
 
[js]


```js
const numbers = new Uint8Array([40, 1, 5, 200]);
const numberSorted = numbers.toSorted();
console.log(numberSorted); // Uint8Array [ 1, 5, 40, 200 ]
// Unlike plain Arrays, a compare function is not required
// to sort the numbers numerically.
console.log(numbers); // Uint8Array [ 40, 1, 5, 200 ]
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.tosorted]](#)

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

`toSorted`

110

110

115

96

16

110

115

74

16

21.0

110

1.31

20.0.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.toSorted` in
    `core-js`](https://github.com/zloirock/core-js#change-array-by-copy)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray.prototype.sort()`](sort)
-   [`TypedArray.prototype.toReversed()`](toreversed)
-   [`TypedArray.prototype.with()`](with)
-   [`Array.prototype.toSorted()`](../array/tosorted)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/toSorted>

