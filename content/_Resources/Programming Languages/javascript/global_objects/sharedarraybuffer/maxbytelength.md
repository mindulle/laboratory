SharedArrayBuffer.prototype.maxByteLength
=========================================

 
The `maxByteLength` accessor property of
[`SharedArrayBuffer`](../sharedarraybuffer) instances returns the
maximum length (in bytes) that this `SharedArrayBuffer` can be grown to.


 
Description
-----------

 
The `maxByteLength` property is an accessor property whose set accessor
function is `undefined`, meaning that you can only read this property.
The value is established when the shared array is constructed, set via
the `maxByteLength` option of the
[`SharedArrayBuffer()`](sharedarraybuffer) constructor, and cannot be
changed.

If this `SharedArrayBuffer` was constructed without specifying a
`maxByteLength` value, this property returns a value equal to the value
of the `SharedArrayBuffer`\'s [`byteLength`](bytelength).



 
Examples
--------


 
### Using maxByteLength 

 
In this example, we create a 8-byte buffer that is resizable to a max
length of 16 bytes, then return its `maxByteLength`:

 
 
[js]


```js
const buffer = new SharedArrayBuffer(8, { maxByteLength: 16 });

buffer.maxByteLength; // 16
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-sharedarraybuffer.prototype.maxbytelength]](https://tc39.es/ecma262/multipage/structured-data.html#sec-get-sharedarraybuffer.prototype.maxbytelength)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`maxByteLength`

111

111

No

97

16.4

111

No

75

16.4

22.0

No

1.33

20.0.0

 
See also 
--------

 
-   [`SharedArrayBuffer`](../sharedarraybuffer)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer/maxByteLength>

