DataView.prototype.setBigUint64()
=================================

 
The `setBigUint64()` method of [`DataView`](../dataview) instances takes
a BigInt and stores it as a 64-bit unsigned integer in the 8 bytes
starting at the specified byte offset of this `DataView`. There is no
alignment constraint; multi-byte values may be stored at any offset
within bounds.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
setBigUint64(byteOffset, value)
setBigUint64(byteOffset, value, littleEndian)
```




 
### Parameters

 

[`byteOffset`](#byteoffset)

:   The offset, in bytes, from the start of the view to store the data
    in.

[`value`](#value)

:   The value to set as a [`BigInt`](../bigint). For how the value is
    encoded in bytes, see [Value encoding and
    normalization](../typedarray#value_encoding_and_normalization).

[`littleEndian`](#littleendian) [Optional]

:   Indicates whether the data is stored in [little- or
    big-endian](https://developer.mozilla.org/en-US/docs/Glossary/Endianness)
    format. If `false` or `undefined`, a big-endian value is written.



 
### Return value 

 
[`undefined`](../undefined).



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if the `byteOffset` is set such that it would store beyond
    the end of the view.



 
Examples
--------


 
### Using setBigUint64() 

 
 
 
[js]


```js
const buffer = new ArrayBuffer(10);
const dataview = new DataView(buffer);
dataview.setBigUint64(0, 3n);
dataview.getBigUint64(1); // 768n
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-dataview.prototype.setbiguint64]](https://tc39.es/ecma262/multipage/structured-data.html#sec-dataview.prototype.setbiguint64)

  -------------------------------------------------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`DataView`](../dataview)
-   [`ArrayBuffer`](../arraybuffer)
-   [`BigUint64Array`](../biguint64array)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/setBigUint64>

