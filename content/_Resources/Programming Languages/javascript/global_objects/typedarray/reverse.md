TypedArray.prototype.reverse()
==============================

 
The `reverse()` method of [`TypedArray`](../typedarray) instances
reverses a typed array *[in
place](https://en.wikipedia.org/wiki/In-place_algorithm)* and returns
the reference to the same typed array, the first typed array element now
becoming the last, and the last typed array element becoming the first.
In other words, elements order in the typed array will be turned towards
the direction opposite to that previously stated. This method has the
same algorithm as [`Array.prototype.reverse()`](../array/reverse).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
reverse()
```




 
### Parameters

 
None.



 
### Return value 

 
The reference to the original typed array, now reversed. Note that the
typed array is reversed *[in
place](https://en.wikipedia.org/wiki/In-place_algorithm)*, and no copy
is made.



 
Description
-----------

 
See [`Array.prototype.reverse()`](../array/reverse) for more details.
This method is not generic and can only be called on typed array
instances.



 
Examples
--------


 
### Using reverse() 

 
 
 
[js]


```js
const uint8 = new Uint8Array([1, 2, 3]);
uint8.reverse();

console.log(uint8); // Uint8Array [3, 2, 1]
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.reverse]](#)

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

`reverse`

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

 
-   [Polyfill of `TypedArray.prototype.reverse` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.join()`](join)
-   [`TypedArray.prototype.sort()`](sort)
-   [`TypedArray.prototype.toReversed()`](toreversed)
-   [`Array.prototype.reverse()`](../array/reverse)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/reverse>

