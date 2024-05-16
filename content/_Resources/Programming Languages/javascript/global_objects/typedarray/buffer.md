TypedArray.prototype.buffer
===========================

 
The `buffer` accessor property of [`TypedArray`](../typedarray)
instances returns the [`ArrayBuffer`](../arraybuffer) or
[`SharedArrayBuffer`](../sharedarraybuffer) referenced by this typed
array at construction time.


 
Try it 
------

 



 
Description
-----------

 
The `buffer` property is an accessor property whose set accessor
function is `undefined`, meaning that you can only read this property.
The value is established when the *TypedArray* is constructed and cannot
be changed. *TypedArray* is one of the [TypedArray
objects](../typedarray#typedarray_objects).

Because a typed array is a *view* of a buffer, the underlying buffer may
be longer than the typed array itself.



 
Examples
--------


 
### Using the buffer property 

 
 
 
[js]


```js
const buffer = new ArrayBuffer(8);
const uint16 = new Uint16Array(buffer);
uint16.buffer; // ArrayBuffer { byteLength: 8 }
```




 
### Accessing the underlying buffer from a sliced array view 

 
 
 
[js]


```js
const buffer = new ArrayBuffer(1024);
const arr = new Uint8Array(buffer, 64, 128);
console.log(arr.byteLength); // 128
console.log(arr.buffer.byteLength); // 1024
console.log(arr.buffer === buffer); // true
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-get-%typedarray%.prototype.buffer]](#)

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

`buffer`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/buffer>

