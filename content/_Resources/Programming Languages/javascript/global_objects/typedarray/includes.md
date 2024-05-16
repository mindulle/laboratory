TypedArray.prototype.includes()
===============================

 
The `includes()` method of [`TypedArray`](../typedarray) instances
determines whether a typed array includes a certain value among its
entries, returning `true` or `false` as appropriate. This method has the
same algorithm as [`Array.prototype.includes()`](../array/includes).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
includes(searchElement)
includes(searchElement, fromIndex)
```




 
### Parameters

 

[`searchElement`](#searchelement)

:   The value to search for.

[`fromIndex`](#fromindex) [Optional]

:   Zero-based index at which to start searching, [converted to an
    integer](../number#integer_conversion).



 
### Return value 

 
A boolean value which is `true` if the value `searchElement` is found
within the typed array (or the part of the typed array indicated by the
index `fromIndex`, if specified).



 
Description
-----------

 
See [`Array.prototype.includes()`](../array/includes) for more details.
This method is not generic and can only be called on typed array
instances.



 
Examples
--------


 
### Using includes() 

 
 
 
[js]


```js
const uint8 = new Uint8Array([1, 2, 3]);
uint8.includes(2); // true
uint8.includes(4); // false
uint8.includes(3, 3); // false

// NaN handling (only true for Float32 and Float64)
new Uint8Array([NaN]).includes(NaN); // false, since the NaN passed to the constructor gets converted to 0
new Float32Array([NaN]).includes(NaN); // true;
new Float64Array([NaN]).includes(NaN); // true;
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.includes]](#)

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

`includes`

47

14

43

34

10

47

43

34

10

5.0

47

1.0

6.0.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.includes` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.indexOf()`](indexof)
-   [`TypedArray.prototype.find()`](find)
-   [`TypedArray.prototype.findIndex()`](findindex)
-   [`Array.prototype.includes()`](../array/includes)
-   [`String.prototype.includes()`](../string/includes)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/includes>

