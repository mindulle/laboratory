TypedArray.prototype.copyWithin()
=================================

 
The `copyWithin()` method of [`TypedArray`](../typedarray) instances
shallow copies part of this typed array to another location in the same
typed array and returns this typed array without modifying its length.
This method has the same algorithm as
[`Array.prototype.copyWithin()`](../array/copywithin).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
copyWithin(target, start)
copyWithin(target, start, end)
```




 
### Parameters

 

[`target`](#target)

:   Zero-based index at which to copy the sequence to, [converted to an
    integer](../number#integer_conversion). This corresponds to where
    the element at `start` will be copied to, and all elements between
    `start` and `end` are copied to succeeding indices.

[`start`](#start)

:   Zero-based index at which to start copying elements from, [converted
    to an integer](../number#integer_conversion).

[`end`](#end) [Optional]

:   Zero-based index at which to end copying elements from, [converted
    to an integer](../number#integer_conversion). `copyWithin()` copies
    up to but not including `end`.



 
### Return value 

 
The modified typed array.



 
Description
-----------

 
See [`Array.prototype.copyWithin()`](../array/copywithin) for more
details. This method is not generic and can only be called on typed
array instances.



 
Examples
--------


 
### Using copyWithin() 

 
 
 
[js]


```js
const buffer = new ArrayBuffer(8);
const uint8 = new Uint8Array(buffer);
uint8.set([1, 2, 3]);
console.log(uint8); // Uint8Array [ 1, 2, 3, 0, 0, 0, 0, 0 ]
uint8.copyWithin(3, 0, 3);
console.log(uint8); // Uint8Array [ 1, 2, 3, 1, 2, 3, 0, 0 ]
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.copywithin]](#)

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

`copyWithin`

45

12

34

32

9.1

45

34

32

9.3

5.0

45

1.0

4.0.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.copyWithin` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`Array.prototype.copyWithin()`](../array/copywithin)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/copyWithin>

