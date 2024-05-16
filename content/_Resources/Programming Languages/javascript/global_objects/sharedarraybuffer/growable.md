SharedArrayBuffer.prototype.growable
====================================

 
The `growable` accessor property of
[`SharedArrayBuffer`](../sharedarraybuffer) instances returns whether
this `SharedArrayBuffer` can be grow or not.


 
Description
-----------

 
The `growable` property is an accessor property whose set accessor
function is `undefined`, meaning that you can only read this property.
The value is established when the array is constructed. If a
`maxByteLength` option was set in the constructor, `growable` will
return `true`; if not, it will return `false`.



 
Examples
--------


 
### Using growable 

 
In this example, we create a 8-byte buffer that is growable to a max
length of 16 bytes, then check its `growable` property, growing it if
`growable` returns `true`:

 
 
[js]


```js
const buffer = new SharedArrayBuffer(8, { maxByteLength: 16 });

if (buffer.growable) {
  console.log("SAB is growable!");
  buffer.grow(12);
}
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-sharedarraybuffer.prototype.growable]](https://tc39.es/ecma262/multipage/structured-data.html#sec-get-sharedarraybuffer.prototype.growable)

  -------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`growable`

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

No

1.33

20.0.0

 
See also 
--------

 
-   [`SharedArrayBuffer`](../sharedarraybuffer)
-   [`SharedArrayBuffer.prototype.grow()`](grow)
-   [`SharedArrayBuffer.prototype.maxByteLength`](maxbytelength)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer/growable>

