TypedArray.prototype.sort()
===========================

 
The `sort()` method of [`TypedArray`](../typedarray) instances sorts the
elements of a typed array *[in
place](https://en.wikipedia.org/wiki/In-place_algorithm)* and returns
the reference to the same typed array, now sorted. This method has the
same algorithm as [`Array.prototype.sort()`](../array/sort), except that
it sorts the values numerically instead of as strings by default.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
sort()
sort(compareFn)
```




 
### Parameters

 

[`compareFn`](#comparefn) [Optional]

:   A function that defines the sort order. The return value should be a
    number whose sign indicates the relative order of the two elements:
    negative if `a` is less than `b`, positive if `a` is greater than
    `b`, and zero if they are equal. `NaN` is treated as `0`. The
    function is called with the following arguments:

    [`a`](#a)

    :   The first element for comparison. Will never be `undefined`.

    [`b`](#b)

    :   The second element for comparison. Will never be `undefined`.

    If omitted, the typed array elements are sorted according to numeric
    value.



 
### Return value 

 
The reference to the original typed array, now sorted. Note that the
typed array is sorted *[in
place](https://en.wikipedia.org/wiki/In-place_algorithm)*, and no copy
is made.



 
Description
-----------

 
See [`Array.prototype.sort()`](../array/sort) for more details. This
method is not generic and can only be called on typed array instances.



 
Examples
--------


 
### Using sort() 

 
For more examples, see also the
[`Array.prototype.sort()`](../array/sort) method.

 
 
[js]


```js
let numbers = new Uint8Array([40, 1, 5, 200]);
numbers.sort();
// Uint8Array [ 1, 5, 40, 200 ]
// Unlike plain Arrays, a compare function is not required
// to sort the numbers numerically.

// Regular Arrays require a compare function to sort numerically:
numbers = [40, 1, 5, 200];
numbers.sort();
// [1, 200, 40, 5]

numbers.sort((a, b) => a - b); // compare numbers
// [ 1, 5, 40, 200 ]
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.sort]](#)

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

`sort`

45

12

46

32

10

45

46

32

10

5.0

45

1.0

4.0.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.sort` with modern behavior like
    stable sort in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.reverse()`](reverse)
-   [`TypedArray.prototype.toSorted()`](tosorted)
-   [`Array.prototype.sort()`](../array/sort)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/sort>

