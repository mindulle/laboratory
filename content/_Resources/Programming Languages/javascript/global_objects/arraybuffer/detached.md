ArrayBuffer.prototype.detached
==============================


The `detached` accessor property of [`ArrayBuffer`](../arraybuffer)
instances returns a boolean indicating whether or not this buffer has
been detached (transferred).



Description
-----------


The `detached` property is an accessor property whose set accessor
function is `undefined`, meaning that you can only read this property.
The value is `false` when the `ArrayBuffer` is first created. The value
becomes `true` if the `ArrayBuffer` is
[transferred](../arraybuffer#transferring_arraybuffers), which detaches
the instance from its underlying memory. Once a buffer becomes detached,
it is no longer usable.




Examples
--------



### Using detached 




[js]


```js
const buffer = new ArrayBuffer(8);
console.log(buffer.detached); // false
const newBuffer = buffer.transfer();
console.log(buffer.detached); // true
console.log(newBuffer.detached); // false
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------
  [ArrayBuffer transfer\
  [\#
  sec-get-arraybuffer.prototype.detached]](https://tc39.es/proposal-arraybuffer-transfer/#sec-get-arraybuffer.prototype.detached)

  -----------------------------------------------------------------------------------------------------------------------------------------


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

`detached`

114

114

122

100

preview

114

122

76

No

23.0

114

No

No


See also 
--------


-   [Polyfill of `ArrayBuffer.prototype.detached` in
    `core-js`](https://github.com/zloirock/core-js#arraybufferprototypetransfer-and-friends)
-   [`ArrayBuffer`](../arraybuffer)
-   [`ArrayBuffer.prototype.transfer()`](transfer)
-   [`ArrayBuffer.prototype.transferToFixedLength()`](transfertofixedlength)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/detached>

