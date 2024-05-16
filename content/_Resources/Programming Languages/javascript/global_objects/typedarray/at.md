TypedArray.prototype.at()
=========================

 
The `at()` method of [`TypedArray`](../typedarray) instances takes an
integer value and returns the item at that index, allowing for positive
and negative integers. Negative integers count back from the last item
in the typed array. This method has the same algorithm as
[`Array.prototype.at()`](../array/at).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
at(index)
```




 
### Parameters

 

[`index`](#index)

:   Zero-based index of the typed array element to be returned,
    [converted to an integer](../number#integer_conversion). Negative
    index counts back from the end of the typed array --- if
    `index < 0`, `index + array.length` is accessed.



 
### Return value 

 
The element in the typed array matching the given index. Always returns
[`undefined`](../undefined) if `index < -array.length` or
`index >= array.length` without attempting to access the corresponding
property.



 
Description
-----------

 
See [`Array.prototype.at()`](../array/at) for more details. This method
is not generic and can only be called on typed array instances.



 
Examples
--------


 
### Return the last value of a typed array 

 
The following example provides a function which returns the last element
found in a specified array.

 
 
[js]


```js
const uint8 = new Uint8Array([1, 2, 4, 7, 11, 18]);

// A function which returns the last item of a given array
function returnLast(arr) {
  return arr.at(-1);
}

const lastItem = returnLast(uint8);
console.log(lastItem); // 18
```




 
### Comparing methods 

 
Here we compare different ways to select the penultimate (last but one)
item of a [`TypedArray`](../typedarray). Whilst all below methods are
valid, it highlights the succinctness and readability of the `at()`
method.

 
 
[js]


```js
// Our typed array with values
const uint8 = new Uint8Array([1, 2, 4, 7, 11, 18]);

// Using length property
const lengthWay = uint8[uint8.length - 2];
console.log(lengthWay); // 11

// Using slice() method. Note an array is returned
const sliceWay = uint8.slice(-2, -1);
console.log(sliceWay[0]); // 11

// Using at() method
const atWay = uint8.at(-2);
console.log(atWay); // 11
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.at]](#)

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

`at`

92

92

90

78

15.4

92

90

65

15.4

16.0

92

No

16.6.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.at` in
    `core-js`](https://github.com/zloirock/core-js#relative-indexing-method)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.findIndex()`](findindex)
-   [`TypedArray.prototype.indexOf()`](indexof)
-   [`TypedArray.prototype.with()`](with)
-   [`Array.prototype.at()`](../array/at)
-   [`String.prototype.at()`](../string/at)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/at>

