ArrayBuffer.prototype.transferToFixedLength()
=============================================


The `transferToFixedLength()` method of [`ArrayBuffer`](../arraybuffer)
instances creates a new non-resizable `ArrayBuffer` with the same byte
content as this buffer, then detaches this buffer.



Syntax
------




[js]


```js
transferToFixedLength()
transferToFixedLength(newByteLength)
```





### Parameters



[`newByteLength`](#newbytelength)

:   The [`byteLength`](bytelength) of the new `ArrayBuffer`. Defaults to
    the `byteLength` of this `ArrayBuffer`.

    -   If `newByteLength` is smaller than the `byteLength` of this
        `ArrayBuffer`, the \"overflowing\" bytes are dropped.
    -   If `newByteLength` is larger than the `byteLength` of this
        `ArrayBuffer`, the extra bytes are filled with zeros.




### Return value 


A new [`ArrayBuffer`](../arraybuffer) object. Its contents are
initialized to the contents of this `ArrayBuffer`, and extra bytes, if
any, are filled with zeros. The new `ArrayBuffer` is always
non-resizable. The original `ArrayBuffer` is detached.




### Exceptions



[`TypeError`](../typeerror)

:   Thrown if this `ArrayBuffer` is already detached.




Description
-----------


Unlike [`transfer()`](transfer), `transferToFixedLength()` always
creates a non-resizable `ArrayBuffer`. This means `newByteLength` can be
larger than the `maxByteLength`, even if this `ArrayBuffer` is
resizable. See [transferring
ArrayBuffers](../arraybuffer#transferring_arraybuffers) for more
information.




Examples
--------



### Transferring a resizable ArrayBuffer to fixed-length 




[js]


```js
const buffer = new ArrayBuffer(8, { maxByteLength: 16 });
const view = new Uint8Array(buffer);
view[1] = 2;
view[7] = 4;

const buffer2 = buffer.transferToFixedLength();
console.log(buffer2.byteLength); // 8
console.log(buffer2.resizable); // false
const view2 = new Uint8Array(buffer2);
console.log(view2[1]); // 2
console.log(view2[7]); // 4
```


Using `transferToFixedLength`, `newByteLength` can be larger than the
`maxByteLength` of the original `ArrayBuffer`.



[js]


```js
const buffer = new ArrayBuffer(8, { maxByteLength: 16 });
const view = new Uint8Array(buffer);
view[1] = 2;
view[7] = 4;

const buffer2 = buffer.transferToFixedLength(20);
console.log(buffer2.byteLength); // 20
console.log(buffer2.resizable); // false
const view2 = new Uint8Array(buffer2);
console.log(view2[1]); // 2
console.log(view2[7]); // 4
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------
  [ArrayBuffer transfer\
  [\#
  sec-arraybuffer.prototype.transfertofixedlength]](https://tc39.es/proposal-arraybuffer-transfer/#sec-arraybuffer.prototype.transfertofixedlength)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------


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

`transferToFixedLength`

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


-   [Polyfill of `ArrayBuffer.prototype.transferToFixedLength()` in
    `core-js`](https://github.com/zloirock/core-js#arraybufferprototypetransfer-and-friends)
-   [`ArrayBuffer`](../arraybuffer)
-   [`ArrayBuffer.prototype.detached`](detached)
-   [`ArrayBuffer.prototype.transfer()`](transfer)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/transferToFixedLength>

