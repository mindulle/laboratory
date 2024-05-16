TypedArray.prototype.lastIndexOf()
==================================

 
The `lastIndexOf()` method of [`TypedArray`](../typedarray) instances
returns the last index at which a given element can be found in the
typed array, or -1 if it is not present. The typed array is searched
backwards, starting at `fromIndex`. This method has the same algorithm
as [`Array.prototype.lastIndexOf()`](../array/lastindexof).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
lastIndexOf(searchElement)
lastIndexOf(searchElement, fromIndex)
```




 
### Parameters

 

[`searchElement`](#searchelement)

:   Element to locate in the typed array.

[`fromIndex`](#fromindex) [Optional]

:   Zero-based index at which to start searching backwards, [converted
    to an integer](../number#integer_conversion).



 
### Return value 

 
The last index of `searchElement` in the typed array; `-1` if not found.



 
Description
-----------

 
See [`Array.prototype.lastIndexOf()`](../array/lastindexof) for more
details. This method is not generic and can only be called on typed
array instances.



 
Examples
--------


 
### Using lastIndexOf() 

 
 
 
[js]


```js
const uint8 = new Uint8Array([2, 5, 9, 2]);
uint8.lastIndexOf(2); // 3
uint8.lastIndexOf(7); // -1
uint8.lastIndexOf(2, 3); // 3
uint8.lastIndexOf(2, 2); // 0
uint8.lastIndexOf(2, -2); // 0
uint8.lastIndexOf(2, -1); // 3
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.lastindexof]](#)

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

`lastIndexOf`

45

12

37Starting with Firefox 47, this method will no longer return `-0`. For
example, `new Uint8Array([0]).lastIndexOf(0, -0)` will now always return
`+0`.

32

10

45

37Starting with Firefox 47, this method will no longer return `-0`. For
example, `new Uint8Array([0]).lastIndexOf(0, -0)` will now always return
`+0`.

32

10

5.0

45

1.0

4.0.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.lastIndexOf` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.findIndex()`](findindex)
-   [`TypedArray.prototype.findLastIndex()`](findlastindex)
-   [`TypedArray.prototype.indexOf()`](indexof)
-   [`Array.prototype.lastIndexOf()`](../array/lastindexof)
-   [`String.prototype.lastIndexOf()`](../string/lastindexof)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/lastIndexOf>

