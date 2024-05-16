ArrayBuffer.prototype.resizable
===============================


The `resizable` accessor property of [`ArrayBuffer`](../arraybuffer)
instances returns whether this array buffer can be resized or not.



Try it 
------






Description
-----------


The `resizable` property is an accessor property whose set accessor
function is `undefined`, meaning that you can only read this property.
The value is established when the array is constructed. If the
`maxByteLength` option was set in the constructor, `resizable` will
return `true`; if not, it will return `false`.




Examples
--------



### Using resizable 


In this example, we create a 8-byte buffer that is resizable to a max
length of 16 bytes, then check its `resizable` property, resizing it if
`resizable` returns `true`:



[js]


```js
const buffer = new ArrayBuffer(8, { maxByteLength: 16 });

if (buffer.resizable) {
  console.log("Buffer is resizable!");
  buffer.resize(12);
}
```




Specifications
--------------


  ---------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-arraybuffer.prototype.resizable]](https://tc39.es/ecma262/multipage/structured-data.html#sec-get-arraybuffer.prototype.resizable)

  ---------------------------------------------------------------------------------------------------------------------------------------------------


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

`resizable`

111

111

No

97

16.4

111

No

75

16.4

22.0

111

1.33

20.0.0


See also 
--------


-   [`ArrayBuffer`](../arraybuffer)
-   [`ArrayBuffer.prototype.maxByteLength`](maxbytelength)
-   [`ArrayBuffer.prototype.resize()`](resize)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/resizable>

