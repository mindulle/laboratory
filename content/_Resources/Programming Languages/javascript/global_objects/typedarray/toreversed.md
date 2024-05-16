TypedArray.prototype.toReversed()
=================================

 
The `toReversed()` method of [`TypedArray`](../typedarray) instances is
the [copying](../array#copying_methods_and_mutating_methods) counterpart
of the [`reverse()`](reverse) method. It returns a new typed array with
the elements in reversed order. This method has the same algorithm as
[`Array.prototype.toReversed()`](../array/toreversed).


 
Syntax
------

 
 
 
[js]


```js
toReversed()
```




 
### Parameters

 
None.



 
### Return value 

 
A new typed array containing the elements in reversed order.



 
Description
-----------

 
See [`Array.prototype.toReversed()`](../array/toreversed) for more
details. This method is not generic and can only be called on typed
array instances.



 
Examples
--------


 
### Using toReversed() 

 
 
 
[js]


```js
const uint8 = new Uint8Array([1, 2, 3]);
const reversedUint8 = uint8.toReversed();
console.log(reversedUint8); // Uint8Array [3, 2, 1]
console.log(uint8); // Uint8Array [1, 2, 3]
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.toreversed]](#)

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

`toReversed`

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

 
-   [Polyfill of `TypedArray.prototype.toReversed` in
    `core-js`](https://github.com/zloirock/core-js#change-array-by-copy)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray.prototype.reverse()`](reverse)
-   [`TypedArray.prototype.toSorted()`](tosorted)
-   [`TypedArray.prototype.with()`](with)
-   [`Array.prototype.toReversed()`](../array/toreversed)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/toReversed>

