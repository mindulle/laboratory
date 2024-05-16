TypedArray.prototype.byteLength
===============================

 
The `byteLength` accessor property of [`TypedArray`](../typedarray)
instances returns the length (in bytes) of this typed array.


 
Try it 
------

 



 
Description
-----------

 
The `byteLength` property is an accessor property whose set accessor
function is `undefined`, meaning that you can only read this property.
The value is established when a *TypedArray* is constructed and cannot
be changed. If the *TypedArray* is not specifying a `byteOffset` or a
`length`, the `length` of the referenced `ArrayBuffer` will be returned.
*TypedArray* is one of the [TypedArray
objects](../typedarray#typedarray_objects).



 
Examples
--------


 
### Using the byteLength property 

 
 
 
[js]


```js
const buffer = new ArrayBuffer(8);

const uint8 = new Uint8Array(buffer);
uint8.byteLength; // 8 (matches the byteLength of the buffer)

const uint8newLength = new Uint8Array(buffer, 1, 5);
uint8newLength.byteLength; // 5 (as specified when constructing the Uint8Array)

const uint8offSet = new Uint8Array(buffer, 2);
uint8offSet.byteLength; // 6 (due to the offset of the constructed Uint8Array)
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-get-%typedarray%.prototype.bytelength]](#)

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

`byteLength`

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

0.10.0

 
See also 
--------

 
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/byteLength>

