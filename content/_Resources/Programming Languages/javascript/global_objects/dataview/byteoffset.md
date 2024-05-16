DataView.prototype.byteOffset
=============================

 
The `byteOffset` accessor property of [`DataView`](../dataview)
instances returns the offset (in bytes) of this view from the start of
its [`ArrayBuffer`](../arraybuffer) or
[`SharedArrayBuffer`](../sharedarraybuffer).


 
Try it 
------

 



 
Description
-----------

 
The `byteOffset` property is an accessor property whose set accessor
function is `undefined`, meaning that you can only read this property.
The value is established when an `DataView` is constructed and cannot be
changed.



 
Examples
--------


 
### Using the byteOffset property 

 
 
 
[js]


```js
const buffer = new ArrayBuffer(8);
const dataview = new DataView(buffer);
dataview.byteOffset; // 0 (no offset specified)

const dataview2 = new DataView(buffer, 3);
dataview2.byteOffset; // 3 (as specified when constructing the DataView)
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-dataview.prototype.byteoffset]](https://tc39.es/ecma262/multipage/structured-data.html#sec-get-dataview.prototype.byteoffset)

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

 
See also 
--------

 
-   [`DataView`](../dataview)
-   [`ArrayBuffer`](../arraybuffer)
-   [`SharedArrayBuffer`](../sharedarraybuffer)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/byteOffset>

