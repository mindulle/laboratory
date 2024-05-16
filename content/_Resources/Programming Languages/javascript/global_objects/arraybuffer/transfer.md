ArrayBuffer.prototype.transfer()
================================


The `transfer()` method of [`ArrayBuffer`](../arraybuffer) instances
creates a new `ArrayBuffer` with the same byte content as this buffer,
then detaches this buffer.



Syntax
------




[js]


```js
transfer()
transfer(newByteLength)
```





### Parameters



[`newByteLength`](#newbytelength) [Optional]

:   The [`byteLength`](bytelength) of the new `ArrayBuffer`. Defaults to
    the `byteLength` of this `ArrayBuffer`.

    -   If `newByteLength` is smaller than the `byteLength` of this
        `ArrayBuffer`, the \"overflowing\" bytes are dropped.
    -   If `newByteLength` is larger than the `byteLength` of this
        `ArrayBuffer`, the extra bytes are filled with zeros.
    -   If this `ArrayBuffer` is resizable, `newByteLength` must not be
        greater than its [`maxByteLength`](maxbytelength).




### Return value 


A new [`ArrayBuffer`](../arraybuffer) object. Its contents are
initialized to the contents of this `ArrayBuffer`, and extra bytes, if
any, are filled with zeros. The new `ArrayBuffer` is resizable if and
only if this `ArrayBuffer` is resizable, in which case its
[`maxByteLength`](maxbytelength) is the same as this `ArrayBuffer`\'s.
The original `ArrayBuffer` is detached.




### Exceptions



[`RangeError`](../rangeerror)

:   Thrown if this `ArrayBuffer` is resizable and `newByteLength` is
    greater than the [`maxByteLength`](maxbytelength) of this
    `ArrayBuffer`.

[`TypeError`](../typeerror)

:   Thrown if this `ArrayBuffer` is already detached.




Description
-----------


The `transfer()` method performs the same operation as the [structured
clone
algorithm](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Structured_clone_algorithm).
It copies the bytes of this `ArrayBuffer` into a new `ArrayBuffer`
object, then detaches this `ArrayBuffer` object. See [transferring
ArrayBuffers](../arraybuffer#transferring_arraybuffers) for more
information.

`transfer()` preserves the resizability of this `ArrayBuffer`. If you
want the new `ArrayBuffer` to be non-resizable, use
[`transferToFixedLength()`](transfertofixedlength) instead. There\'s no
way to transfer a buffer that makes a fixed-length buffer become
resizable.

`transfer()` is very efficient because implementations may implement
this method as a zero-copy move or a `realloc` --- there does not need
to be an actual copy of the data.




Examples
--------



### Transferring an ArrayBuffer 




[js]


```js
// Create an ArrayBuffer and write a few bytes
const buffer = new ArrayBuffer(8);
const view = new Uint8Array(buffer);
view[1] = 2;
view[7] = 4;

// Copy the buffer to the same size
const buffer2 = buffer.transfer();
console.log(buffer.detached); // true
console.log(buffer2.byteLength); // 8
const view2 = new Uint8Array(buffer2);
console.log(view2[1]); // 2
console.log(view2[7]); // 4

// Copy the buffer to a smaller size
const buffer3 = buffer2.transfer(4);
console.log(buffer3.byteLength); // 4
const view3 = new Uint8Array(buffer3);
console.log(view3[1]); // 2
console.log(view3[7]); // undefined

// Copy the buffer to a larger size
const buffer4 = buffer3.transfer(8);
console.log(buffer4.byteLength); // 8
const view4 = new Uint8Array(buffer4);
console.log(view4[1]); // 2
console.log(view4[7]); // 0

// Already detached, throws TypeError
buffer.transfer(); // TypeError: Cannot perform ArrayBuffer.prototype.transfer on a detached ArrayBuffer
```





### Transferring a resizable ArrayBuffer 




[js]


```js
const buffer = new ArrayBuffer(8, { maxByteLength: 16 });
const view = new Uint8Array(buffer);
view[1] = 2;
view[7] = 4;

// Copy the buffer to a smaller size
const buffer2 = buffer.transfer(4);
console.log(buffer2.byteLength); // 4
console.log(buffer2.maxByteLength); // 16
const view2 = new Uint8Array(buffer2);
console.log(view2[1]); // 2
console.log(view2[7]); // undefined
buffer2.resize(8);
console.log(view2[7]); // 0

// Copy the buffer to a larger size within maxByteLength
const buffer3 = buffer2.transfer(12);
console.log(buffer3.byteLength); // 12

// Copy the buffer to a larger size than maxByteLength
buffer3.transfer(20); // RangeError: Invalid array buffer length
```




Specifications
--------------


  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ArrayBuffer transfer\
  [\#
  sec-arraybuffer.prototype.transfer]](https://tc39.es/proposal-arraybuffer-transfer/#sec-arraybuffer.prototype.transfer)

  ---------------------------------------------------------------------------------------------------------------------------------


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

`transfer`

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


-   [Polyfill of `ArrayBuffer.prototype.transfer()` in
    `core-js`](https://github.com/zloirock/core-js#arraybufferprototypetransfer-and-friends)
-   [`ArrayBuffer`](../arraybuffer)
-   [`ArrayBuffer.prototype.detached`](detached)
-   [`ArrayBuffer.prototype.transferToFixedLength()`](transfertofixedlength)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/transfer>

