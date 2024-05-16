TypedArray.prototype.join()
===========================

 
The `join()` method of [`TypedArray`](../typedarray) instances creates
and returns a new string by concatenating all of the elements in this
typed array, separated by commas or a specified separator string. If the
typed array has only one item, then that item will be returned without
using the separator. This method has the same algorithm as
[`Array.prototype.join()`](../array/join).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
join()
join(separator)
```




 
### Parameters

 

[`separator`](#separator) [Optional]

:   A string to separate each pair of adjacent elements of the typed
    array. If omitted, the typed array elements are separated with a
    comma (\",\").



 
### Return value 

 
A string with all typed array elements joined. If `array.length` is `0`,
the empty string is returned.



 
Description
-----------

 
See [`Array.prototype.join()`](../array/join) for more details. This
method is not generic and can only be called on typed array instances.



 
Examples
--------


 
### Using join() 

 
 
 
[js]


```js
const uint8 = new Uint8Array([1, 2, 3]);
uint8.join(); // '1,2,3'
uint8.join(" / "); // '1 / 2 / 3'
uint8.join(""); // '123'
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.join]](#)

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

`join`

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

 
-   [Polyfill of `TypedArray.prototype.join` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.toString()`](tostring)
-   [`Array.prototype.join()`](../array/join)
-   [`String.prototype.split()`](../string/split)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/join>

