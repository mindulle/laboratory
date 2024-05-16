TypedArray.prototype.slice()
============================

 
The `slice()` method of [`TypedArray`](../typedarray) instances returns
a copy of a portion of a typed array into a new typed array object
selected from `start` to `end` (`end` not included) where `start` and
`end` represent the index of items in that typed array. The original
typed array will not be modified. This method has the same algorithm as
[`Array.prototype.slice()`](../array/slice).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
slice()
slice(start)
slice(start, end)
```




 
### Parameters

 

[`start`](#start) [Optional]

:   Zero-based index at which to start extraction, [converted to an
    integer](../number#integer_conversion).

[`end`](#end) [Optional]

:   Zero-based index at which to end extraction, [converted to an
    integer](../number#integer_conversion). `slice()` extracts up to but
    not including `end`.



 
### Return value 

 
A new typed array containing the extracted elements.



 
Description
-----------

 
See [`Array.prototype.slice()`](../array/slice) for more details. This
method is not generic and can only be called on typed array instances.



 
Examples
--------


 
### Return a portion of an existing typed array 

 
 
 
[js]


```js
const uint8 = new Uint8Array([1, 2, 3]);
uint8.slice(1); // Uint8Array [ 2, 3 ]
uint8.slice(2); // Uint8Array [ 3 ]
uint8.slice(-2); // Uint8Array [ 2, 3 ]
uint8.slice(0, 1); // Uint8Array [ 1 ]
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.slice]](#)

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

`slice`

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

 
-   [Polyfill of `TypedArray.prototype.slice` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`Array.prototype.slice()`](../array/slice)
-   [`String.prototype.slice()`](../string/slice)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/slice>

