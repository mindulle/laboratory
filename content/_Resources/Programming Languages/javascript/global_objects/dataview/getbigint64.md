DataView.prototype.getBigInt64()
================================

 
The `getBigInt64()` method of [`DataView`](../dataview) instances reads
8 bytes starting at the specified byte offset of this `DataView` and
interprets them as a 64-bit signed integer. There is no alignment
constraint; multi-byte values may be fetched from any offset within
bounds.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
getBigInt64(byteOffset)
getBigInt64(byteOffset, littleEndian)
```




 
### Parameters

 

[`byteOffset`](#byteoffset)

:   The offset, in bytes, from the start of the view to read the data
    from.

[`littleEndian`](#littleendian) [Optional]

:   Indicates whether the data is stored in [little- or
    big-endian](https://developer.mozilla.org/en-US/docs/Glossary/Endianness)
    format. If `false` or `undefined`, a big-endian value is read.



 
### Return value 

 
A [`BigInt`](../bigint) from -2^63^ to 2^63^-1, inclusive.



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if the `byteOffset` is set such that it would read beyond the
    end of the view.



 
Examples
--------


 
### Using getBigInt64() 

 
 
 
[js]


```js
const { buffer } = new Uint8Array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9]);
const dataview = new DataView(buffer);
console.log(dataview.getBigInt64(1)); // 72623859790382856n
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-dataview.prototype.getbigint64]](https://tc39.es/ecma262/multipage/structured-data.html#sec-dataview.prototype.getbigint64)

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

 
See also 
--------

 
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`DataView`](../dataview)
-   [`ArrayBuffer`](../arraybuffer)
-   [`BigInt64Array`](../bigint64array)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/getBigInt64>

