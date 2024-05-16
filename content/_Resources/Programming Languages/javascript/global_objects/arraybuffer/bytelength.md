ArrayBuffer.prototype.byteLength
================================


The `byteLength` accessor property of [`ArrayBuffer`](../arraybuffer)
instances returns the length (in bytes) of this array buffer.



Try it 
------






Description
-----------


The `byteLength` property is an accessor property whose set accessor
function is `undefined`, meaning that you can only read this property.
The value is established when the array is constructed and cannot be
changed. This property returns 0 if this `ArrayBuffer` has been
detached.




Examples
--------



### Using byteLength 




[js]


```js
const buffer = new ArrayBuffer(8);
buffer.byteLength; // 8
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-arraybuffer.prototype.bytelength]](https://tc39.es/ecma262/multipage/structured-data.html#sec-get-arraybuffer.prototype.bytelength)

  -----------------------------------------------------------------------------------------------------------------------------------------------------


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


-   [`ArrayBuffer`](../arraybuffer)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/byteLength>

