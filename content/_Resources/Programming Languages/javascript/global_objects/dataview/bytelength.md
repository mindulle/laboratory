DataView.prototype.byteLength
=============================

 
The `byteLength` accessor property of [`DataView`](../dataview)
instances returns the length (in bytes) of this view.


 
Try it 
------

 



 
Description
-----------

 
The `byteLength` property is an accessor property whose set accessor
function is `undefined`, meaning that you can only read this property.
The value is established when an `DataView` is constructed and cannot be
changed. If the `DataView` is not specifying an offset or a
`byteLength`, the `byteLength` of the referenced `ArrayBuffer` or
`SharedArrayBuffer` will be returned.



 
Examples
--------


 
### Using the byteLength property 

 
 
 
[js]


```js
const buffer = new ArrayBuffer(8);
const dataview = new DataView(buffer);
dataview.byteLength; // 8 (matches the byteLength of the buffer)

const dataview2 = new DataView(buffer, 1, 5);
dataview2.byteLength; // 5 (as specified when constructing the DataView)

const dataview3 = new DataView(buffer, 2);
dataview3.byteLength; // 6 (due to the offset of the constructed DataView)
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-dataview.prototype.bytelength]](https://tc39.es/ecma262/multipage/structured-data.html#sec-get-dataview.prototype.bytelength)

  -----------------------------------------------------------------------------------------------------------------------------------------------


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

 
-   [`DataView`](../dataview)
-   [`ArrayBuffer`](../arraybuffer)
-   [`SharedArrayBuffer`](../sharedarraybuffer)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/byteLength>

