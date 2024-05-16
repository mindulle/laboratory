TypedArray.prototype.fill()
===========================

 
The `fill()` method of [`TypedArray`](../typedarray) instances changes
all elements within a range of indices in a typed array to a static
value. It returns the modified typed array. This method has the same
algorithm as [`Array.prototype.fill()`](../array/fill).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
fill(value)
fill(value, start)
fill(value, start, end)
```




 
### Parameters

 

[`value`](#value)

:   Value to fill the typed array with.

[`start`](#start) [Optional]

:   Zero-based index at which to start filling, [converted to an
    integer](../number#integer_conversion).

[`end`](#end) [Optional]

:   Zero-based index at which to end filling, [converted to an
    integer](../number#integer_conversion). `fill()` fills up to but not
    including `end`.



 
### Return value 

 
The modified typed array, filled with `value`.



 
Description
-----------

 
See [`Array.prototype.fill()`](../array/fill) for more details. This
method is not generic and can only be called on typed array instances.



 
Examples
--------


 
### Using fill() 

 
 
 
[js]


```js
new Uint8Array([1, 2, 3]).fill(4); // Uint8Array [4, 4, 4]
new Uint8Array([1, 2, 3]).fill(4, 1); // Uint8Array [1, 4, 4]
new Uint8Array([1, 2, 3]).fill(4, 1, 2); // Uint8Array [1, 4, 3]
new Uint8Array([1, 2, 3]).fill(4, 1, 1); // Uint8Array [1, 2, 3]
new Uint8Array([1, 2, 3]).fill(4, -3, -2); // Uint8Array [4, 2, 3]
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.fill]](#)

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

`fill`

45

12

37

32

9.1

45

37

32

9.3

5.0

45

1.0

4.0.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.fill` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`Array.prototype.fill()`](../array/fill)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/fill>

