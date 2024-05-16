DataView.prototype.setUint8()
=============================

 
The `setUint8()` method of [`DataView`](../dataview) instances takes a
number and stores it as an 8-bit unsigned integer in the byte at the
specified byte offset of this `DataView`.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
setUint8(byteOffset, value)
```




 
### Parameters

 

[`byteOffset`](#byteoffset)

:   The offset, in bytes, from the start of the view to store the data
    in.

[`value`](#value)

:   The value to set. For how the value is encoded in bytes, see [Value
    encoding and
    normalization](../typedarray#value_encoding_and_normalization).



 
### Return value 

 
[`undefined`](../undefined).



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if the `byteOffset` is set such that it would store beyond
    the end of the view.



 
Examples
--------


 
### Using setUint8() 

 
 
 
[js]


```js
const buffer = new ArrayBuffer(10);
const dataview = new DataView(buffer);
dataview.setUint8(0, 3);
dataview.getUint8(0); // 3
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-dataview.prototype.setuint8]](https://tc39.es/ecma262/multipage/structured-data.html#sec-dataview.prototype.setuint8)

  -----------------------------------------------------------------------------------------------------------------------------------


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

 
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`DataView`](../dataview)
-   [`ArrayBuffer`](../arraybuffer)
-   [`Uint8Array`](../uint8array)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/setUint8>

