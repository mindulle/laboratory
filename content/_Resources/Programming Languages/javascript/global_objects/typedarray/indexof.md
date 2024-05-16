TypedArray.prototype.indexOf()
==============================

 
The `indexOf()` method of [`TypedArray`](../typedarray) instances
returns the first index at which a given element can be found in the
typed array, or -1 if it is not present. This method has the same
algorithm as [`Array.prototype.indexOf()`](../array/indexof).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
indexOf(searchElement)
indexOf(searchElement, fromIndex)
```




 
### Parameters

 

[`searchElement`](#searchelement)

:   Element to locate in the typed array.

[`fromIndex`](#fromindex) [Optional]

:   Zero-based index at which to start searching, [converted to an
    integer](../number#integer_conversion).



 
### Return value 

 
The first index of `searchElement` in the typed array; `-1` if not
found.



 
Description
-----------

 
See [`Array.prototype.indexOf()`](../array/indexof) for more details.
This method is not generic and can only be called on typed array
instances.



 
Examples
--------


 
### Using indexOf() 

 
 
 
[js]


```js
const uint8 = new Uint8Array([2, 5, 9]);
uint8.indexOf(2); // 0
uint8.indexOf(7); // -1
uint8.indexOf(9, 2); // 2
uint8.indexOf(2, -1); // -1
uint8.indexOf(2, -3); // 0
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.indexof]](#)

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

`indexOf`

45

12

37Starting with Firefox 47, this method will no longer return `-0`. For
example, `new Uint8Array([0]).indexOf(0, -0)` will now always return
`+0`.

32

9.1

45

37Starting with Firefox 47, this method will no longer return `-0`. For
example, `new Uint8Array([0]).indexOf(0, -0)` will now always return
`+0`.

32

9.3

5.0

45

1.0

4.0.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.indexOf` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.findIndex()`](findindex)
-   [`TypedArray.prototype.findLastIndex()`](findlastindex)
-   [`TypedArray.prototype.lastIndexOf()`](lastindexof)
-   [`Array.prototype.indexOf()`](../array/indexof)
-   [`String.prototype.indexOf()`](../string/indexof)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/indexOf>

