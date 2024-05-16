DataView.prototype.getUint8()
=============================

 
The `getUint8()` method of [`DataView`](../dataview) instances reads 1
byte at the specified byte offset of this `DataView` and interprets it
as an 8-bit unsigned integer.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
getUint8(byteOffset)
```




 
### Parameters

 

[`byteOffset`](#byteoffset)

:   The offset, in bytes, from the start of the view to read the data
    from.



 
### Return value 

 
An integer from 0 to 255, inclusive.



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if the `byteOffset` is set such that it would read beyond the
    end of the view.



 
Examples
--------


 
### Using getUint8() 

 
 
 
[js]


```js
const { buffer } = new Uint8Array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9]);
const dataview = new DataView(buffer);
console.log(dataview.getUint8(1)); // 1
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-dataview.prototype.getuint8]](https://tc39.es/ecma262/multipage/structured-data.html#sec-dataview.prototype.getuint8)

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/getUint8>

