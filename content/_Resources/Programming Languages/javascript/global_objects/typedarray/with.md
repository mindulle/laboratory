TypedArray.prototype.with()
===========================

 
The `with()` method of [`TypedArray`](../typedarray) instances is the
[copying](../array#copying_methods_and_mutating_methods) version of
using the [bracket
notation](../../operators/property_accessors#bracket_notation) to change
the value of a given index. It returns a new typed array with the
element at the given index replaced with the given value. This method
has the same algorithm as [`Array.prototype.with()`](../array/with).


 
Syntax
------

 
 
 
[js]


```js
arrayInstance.with(index, value)
```




 
### Parameters

 

[`index`](#index)

:   Zero-based index at which to change the typed array, [converted to
    an integer](../number#integer_conversion).

[`value`](#value)

:   Any value to be assigned to the given index.



 
### Return value 

 
A new typed array with the element at `index` replaced with `value`.



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if `index >= array.length` or `index < -array.length`.



 
Description
-----------

 
See [`Array.prototype.with()`](../array/with) for more details. This
method is not generic and can only be called on typed array instances.



 
Examples
--------


 
### Using with() 

 
 
 
[js]


```js
const arr = new Uint8Array([1, 2, 3, 4, 5]);
console.log(arr.with(2, 6)); // Uint8Array [1, 2, 6, 4, 5]
console.log(arr); // Uint8Array [1, 2, 3, 4, 5]
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.with]](#)

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

`with`

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

 
-   [Polyfill of `TypedArray.prototype.with` in
    `core-js`](https://github.com/zloirock/core-js#change-array-by-copy)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray.prototype.toReversed()`](toreversed)
-   [`TypedArray.prototype.toSorted()`](tosorted)
-   [`TypedArray.prototype.at()`](at)
-   [`Array.prototype.with()`](../array/with)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/with>

