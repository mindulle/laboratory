TypedArray.prototype.subarray()
===============================

 
The `subarray()` method of [`TypedArray`](../typedarray) instances
returns a new typed array on the same [`ArrayBuffer`](../arraybuffer)
store and with the same element types as for this typed array. The begin
offset is **inclusive** and the end offset is **exclusive**.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
subarray()
subarray(begin)
subarray(begin, end)
```




 
### Parameters

 

[`begin`](#begin) [Optional]

:   Element to begin at. The offset is inclusive. The whole array will
    be included in the new view if this value is not specified.

[`end`](#end) [Optional]

:   Element to end at. The offset is exclusive. If not specified, all
    elements from the one specified by `begin` to the end of the array
    are included in the new view.



 
### Return value 

 
A new [`TypedArray`](../typedarray) object.



 
Description
-----------

 
The range specified by `begin` and `end` is clamped to the valid index
range for the current array; if the computed length of the new array
would be negative, it\'s clamped to zero. If either `begin` or `end` is
negative, it refers to an index from the end of the array instead of
from the beginning.

Also note that this is creating a new view on the existing buffer;
changes to the new object\'s contents will impact the original object
and vice versa.



 
Examples
--------


 
### Using the subarray() method 

 
 
 
[js]


```js
const buffer = new ArrayBuffer(8);
const uint8 = new Uint8Array(buffer);
uint8.set([1, 2, 3]);

console.log(uint8); // Uint8Array [ 1, 2, 3, 0, 0, 0, 0, 0 ]

const sub = uint8.subarray(0, 4);

console.log(sub); // Uint8Array [ 1, 2, 3, 0 ]
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.subarray]](#)

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

`subarray`

7

12

4

11.6

5.1

18

4

12

4.2

1.0

4

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.subarray` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`ArrayBuffer`](../arraybuffer)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/subarray>

