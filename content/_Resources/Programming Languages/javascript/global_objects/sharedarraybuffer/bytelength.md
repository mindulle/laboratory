SharedArrayBuffer.prototype.byteLength
======================================

 
The `byteLength` accessor property of
[`SharedArrayBuffer`](../sharedarraybuffer) instances returns the length
(in bytes) of this `SharedArrayBuffer`.


 
Try it 
------

 



 
Description
-----------

 
The `byteLength` property is an accessor property whose set accessor
function is `undefined`, meaning that you can only read this property.
The value is established when the shared array is constructed and cannot
be changed.



 
Examples
--------


 
### Using byteLength 

 
 
 
[js]


```js
const sab = new SharedArrayBuffer(1024);
sab.byteLength; // 1024
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-sharedarraybuffer.prototype.bytelength]](https://tc39.es/ecma262/multipage/structured-data.html#sec-get-sharedarraybuffer.prototype.bytelength)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------


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

68

79

79

55

15.2

89

79

63

15.2

15.0

No

1.0

8.10.0

 
See also 
--------

 
-   [`SharedArrayBuffer`](../sharedarraybuffer)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer/byteLength>

