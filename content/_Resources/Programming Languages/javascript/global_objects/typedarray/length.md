TypedArray.prototype.length
===========================

 
The `length` accessor property of [`TypedArray`](../typedarray)
instances returns the length (in elements) of this typed array.


 
Try it 
------

 



 
Description
-----------

 
The `length` property is an accessor property whose set accessor
function is `undefined`, meaning that you can only read this property.
The value is established when a *TypedArray* is constructed and cannot
be changed. If the *TypedArray* is not specifying a `byteOffset` or a
`length`, the length of the referenced [`ArrayBuffer`](../arraybuffer)
will be returned. *TypedArray* is one of the [TypedArray
objects](../typedarray#typedarray_objects).



 
Examples
--------


 
### Using the `length` property 

 
 
 
[js]


```js
const buffer = new ArrayBuffer(8);

let uint8 = new Uint8Array(buffer);
uint8.length; // 8 (matches the length of the buffer)

uint8 = new Uint8Array(buffer, 1, 5);
uint8.length; // 5 (as specified when constructing the Uint8Array)

uint8 = new Uint8Array(buffer, 2);
uint8.length; // 6 (due to the offset of the constructed Uint8Array)
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-get-%typedarray%.prototype.length]](#)

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

`length`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/length>

