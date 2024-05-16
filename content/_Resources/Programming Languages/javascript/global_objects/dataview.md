DataView
========

 
The `DataView` view provides a low-level interface for reading and
writing multiple number types in a binary [`ArrayBuffer`](arraybuffer),
without having to care about the platform\'s
[endianness](https://developer.mozilla.org/en-US/docs/Glossary/Endianness).


 
Description
-----------


 
### Endianness

 
Multi-byte number formats are represented in memory differently
depending on machine architecture --- see
[Endianness](https://developer.mozilla.org/en-US/docs/Glossary/Endianness)
for an explanation. `DataView` accessors provide explicit control of how
data is accessed, regardless of the executing computer\'s endianness.

 
 
[js]


```js
const littleEndian = (() => {
  const buffer = new ArrayBuffer(2);
  new DataView(buffer).setInt16(0, 256, true /* littleEndian */);
  // Int16Array uses the platform's endianness.
  return new Int16Array(buffer)[0] === 256;
})();
console.log(littleEndian); // true or false
```




 
### 64-bit Integer Values 

 
Some browsers don\'t have support for
[`DataView.prototype.setBigInt64()`](dataview/setbigint64) and
[`DataView.prototype.setBigUint64()`](dataview/setbiguint64). So to
enable 64-bit operations in your code that will work across browsers,
you could implement your own `getUint64()` function, to obtain values
with precision up to
[`Number.MAX_SAFE_INTEGER`](number/max_safe_integer) --- which could
suffice for certain cases.

 
 
[js]


```js
function getUint64(dataview, byteOffset, littleEndian) {
  // split 64-bit number into two 32-bit (4-byte) parts
  const left = dataview.getUint32(byteOffset, littleEndian);
  const right = dataview.getUint32(byteOffset + 4, littleEndian);

  // combine the two 32-bit values
  const combined = littleEndian
    ? left + 2 ** 32 * right
    : 2 ** 32 * left + right;

  if (!Number.isSafeInteger(combined))
    console.warn(combined, "exceeds MAX_SAFE_INTEGER. Precision may be lost");

  return combined;
}
```


Alternatively, if you need full 64-bit range, you can create a
[`BigInt`](bigint). Further, although native BigInts are much faster
than user-land library equivalents, BigInts will always be much slower
than 32-bit integers in JavaScript due to the nature of their variable
size.

 
 
[js]


```js
const BigInt = window.BigInt,
  bigThirtyTwo = BigInt(32),
  bigZero = BigInt(0);
function getUint64BigInt(dataview, byteOffset, littleEndian) {
  // split 64-bit number into two 32-bit (4-byte) parts
  const left = BigInt(dataview.getUint32(byteOffset | 0, !!littleEndian) >>> 0);
  const right = BigInt(
    dataview.getUint32(((byteOffset | 0) + 4) | 0, !!littleEndian) >>> 0,
  );

  // combine the two 32-bit values and return
  return littleEndian
    ? (right << bigThirtyTwo) | left
    : (left << bigThirtyTwo) | right;
}
```




 
Constructor
-----------

 

[`DataView()`](dataview/dataview)

:   Creates a new `DataView` object.



 
Instance properties 
-------------------

 
These properties are defined on `DataView.prototype` and shared by all
`DataView` instances.

[`DataView.prototype.buffer`](dataview/buffer)

:   The [`ArrayBuffer`](arraybuffer) referenced by this view. Fixed at
    construction time and thus **read only.**

[`DataView.prototype.byteLength`](dataview/bytelength)

:   The length (in bytes) of this view. Fixed at construction time and
    thus **read only.**

[`DataView.prototype.byteOffset`](dataview/byteoffset)

:   The offset (in bytes) of this view from the start of its
    [`ArrayBuffer`](arraybuffer). Fixed at construction time and thus
    **read only.**

[`DataView.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `DataView` instances, the initial value is the
    [`DataView`](dataview/dataview) constructor.

[`DataView.prototype[@@toStringTag]`](#dataview.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"DataView"`. This property is used in
    [`Object.prototype.toString()`](object/tostring).



 
Instance methods 
----------------

 

[`DataView.prototype.getBigInt64()`](dataview/getbigint64)

:   Reads 8 bytes starting at the specified byte offset of this
    `DataView` and interprets them as a 64-bit signed integer.

[`DataView.prototype.getBigUint64()`](dataview/getbiguint64)

:   Reads 8 bytes starting at the specified byte offset of this
    `DataView` and interprets them as a 64-bit unsigned integer.

[`DataView.prototype.getFloat32()`](dataview/getfloat32)

:   Reads 4 bytes starting at the specified byte offset of this
    `DataView` and interprets them as a 32-bit floating point number.

[`DataView.prototype.getFloat64()`](dataview/getfloat64)

:   Reads 8 bytes starting at the specified byte offset of this
    `DataView` and interprets them as a 64-bit floating point number.

[`DataView.prototype.getInt16()`](dataview/getint16)

:   Reads 2 bytes starting at the specified byte offset of this
    `DataView` and interprets them as a 16-bit signed integer.

[`DataView.prototype.getInt32()`](dataview/getint32)

:   Reads 4 bytes starting at the specified byte offset of this
    `DataView` and interprets them as a 32-bit signed integer.

[`DataView.prototype.getInt8()`](dataview/getint8)

:   Reads 1 byte at the specified byte offset of this `DataView` and
    interprets it as an 8-bit signed integer.

[`DataView.prototype.getUint16()`](dataview/getuint16)

:   Reads 2 bytes starting at the specified byte offset of this
    `DataView` and interprets them as a 16-bit unsigned integer.

[`DataView.prototype.getUint32()`](dataview/getuint32)

:   Reads 4 bytes starting at the specified byte offset of this
    `DataView` and interprets them as a 32-bit unsigned integer.

[`DataView.prototype.getUint8()`](dataview/getuint8)

:   Reads 1 byte at the specified byte offset of this `DataView` and
    interprets it as an 8-bit unsigned integer.

[`DataView.prototype.setBigInt64()`](dataview/setbigint64)

:   Takes a BigInt and stores it as a 64-bit signed integer in the 8
    bytes starting at the specified byte offset of this `DataView`.

[`DataView.prototype.setBigUint64()`](dataview/setbiguint64)

:   Takes a BigInt and stores it as a 64-bit unsigned integer in the 8
    bytes starting at the specified byte offset of this `DataView`.

[`DataView.prototype.setFloat32()`](dataview/setfloat32)

:   Takes a number and stores it as a 32-bit float in the 4 bytes
    starting at the specified byte offset of this `DataView`.

[`DataView.prototype.setFloat64()`](dataview/setfloat64)

:   Takes a number and stores it as a 64-bit float in the 8 bytes
    starting at the specified byte offset of this `DataView`.

[`DataView.prototype.setInt16()`](dataview/setint16)

:   Takes a number and stores it as a 16-bit signed integer in the 2
    bytes at the specified byte offset of this `DataView`.

[`DataView.prototype.setInt32()`](dataview/setint32)

:   Takes a number and stores it as a 32-bit signed integer in the 4
    bytes at the specified byte offset of this `DataView`.

[`DataView.prototype.setInt8()`](dataview/setint8)

:   Takes a number and stores it as an 8-bit signed integer in the byte
    at the specified byte offset of this `DataView`.

[`DataView.prototype.setUint16()`](dataview/setuint16)

:   Takes a number and stores it as a 16-bit unsigned integer in the 2
    bytes at the specified byte offset of this `DataView`.

[`DataView.prototype.setUint32()`](dataview/setuint32)

:   Takes a number and stores it as a 32-bit unsigned integer in the 4
    bytes at the specified byte offset of this `DataView`.

[`DataView.prototype.setUint8()`](dataview/setuint8)

:   Takes a number and stores it as an 8-bit unsigned integer in the
    byte at the specified byte offset of this `DataView`.



 
Examples
--------


 
### Using DataView 

 
 
 
[js]


```js
const buffer = new ArrayBuffer(16);
const view = new DataView(buffer, 0);

view.setInt16(1, 42);
view.getInt16(1); // 42
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-dataview-objects]](https://tc39.es/ecma262/multipage/structured-data.html#sec-dataview-objects)

  -------------------------------------------------------------------------------------------------------------


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

`DataView`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`DataView`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`buffer`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`byteLength`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`byteOffset`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`getBigInt64`

67

79

68

54

15

67

68

48

15

9.0

67

1.0

10.4.0

`getBigUint64`

67

79

68

54

15

67

68

48

15

9.0

67

1.0

10.4.0

`getFloat32`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`getFloat64`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`getInt16`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`getInt32`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`getInt8`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`getUint16`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`getUint32`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`getUint8`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`setBigInt64`

67

79

68

54

15

67

68

48

15

9.0

67

1.0

10.4.0

`setBigUint64`

67

79

68

54

15

67

68

48

15

9.0

67

1.0

10.4.0

`setFloat32`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`setFloat64`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`setInt16`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`setInt32`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`setInt8`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`setUint16`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`setUint32`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

`setUint8`

9

12

15

12.1

5.1

18

15

12.1

5

1.0

4

1.0

0.10.0

 
See also 
--------

 
-   [Polyfill of `DataView` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [`ArrayBuffer`](arraybuffer)
-   [`SharedArrayBuffer`](sharedarraybuffer)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView>

