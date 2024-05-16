DataView.prototype.buffer
=========================

 
The `buffer` accessor property of [`DataView`](../dataview) instances
returns the [`ArrayBuffer`](../arraybuffer) or
[`SharedArrayBuffer`](../sharedarraybuffer) referenced by this view at
construction time.


 
Try it 
------

 



 
Description
-----------

 
The `buffer` property is an accessor property whose set accessor
function is `undefined`, meaning that you can only read this property.
The value is established when the `DataView` is constructed and cannot
be changed.



 
Examples
--------


 
### Using the buffer property 

 
 
 
[js]


```js
const buffer = new ArrayBuffer(8);
const dataview = new DataView(buffer);
dataview.buffer; // ArrayBuffer { byteLength: 8 }
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-dataview.prototype.buffer]](https://tc39.es/ecma262/multipage/structured-data.html#sec-get-dataview.prototype.buffer)

  ---------------------------------------------------------------------------------------------------------------------------------------


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

`sharedarraybuffer_support`

60

79

79

47

10.1--11.1

60

79

44

10.3--11.3

8.0

60

1.0

8.10.0

 
See also 
--------

 
-   [`DataView`](../dataview)
-   [`ArrayBuffer`](../arraybuffer)
-   [`SharedArrayBuffer`](../sharedarraybuffer)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/buffer>

