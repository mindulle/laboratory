TypedArray.prototype.byteOffset
===============================

 
The `byteOffset` accessor property of [`TypedArray`](../typedarray)
instances returns the offset (in bytes) of this typed array from the
start of its [`ArrayBuffer`](../arraybuffer) or
[`SharedArrayBuffer`](../sharedarraybuffer).


 
Description
-----------

 
The `byteOffset` property is an accessor property whose set accessor
function is `undefined`, meaning that you can only read this property.
The value is established when a *TypedArray* is constructed and cannot
be changed. *TypedArray* is one of the [TypedArray
objects](../typedarray#typedarray_objects).



 
Examples
--------


 
### Using the byteOffset property 

 
 
 
[js]


```js
const buffer = new ArrayBuffer(8);

const uint8array1 = new Uint8Array(buffer);
uint8array1.byteOffset; // 0 (no offset specified)

const uint8array2 = new Uint8Array(buffer, 3);
uint8array2.byteOffset; // 3 (as specified when constructing Uint8Array)
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-get-%typedarray%.prototype.byteoffset]](#)

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

`byteOffset`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/byteOffset>

