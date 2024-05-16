ArrayBuffer.prototype.resize()
==============================


The `resize()` method of [`ArrayBuffer`](../arraybuffer) instances
resizes the `ArrayBuffer` to the specified size, in bytes.



Try it 
------






Syntax
------




[js]


```js
resize(newLength)
```





### Parameters



[`newLength`](#newlength)

:   The new length, in bytes, to resize the `ArrayBuffer` to.




### Return value 


None ([`undefined`](../undefined)).




### Exceptions



[`TypeError`](../typeerror)

:   Thrown if the `ArrayBuffer` is detached or is not resizable.

[`RangeError`](../rangeerror)

:   Thrown if `newLength` is larger than the
    [`maxByteLength`](maxbytelength) of the `ArrayBuffer`.




Description
-----------


The `resize()` method resizes an `ArrayBuffer` to the size specified by
the `newLength` parameter, provided that the `ArrayBuffer` is
[resizable](resizable) and the new size is less than or equal to the
[`maxByteLength`](maxbytelength) of the `ArrayBuffer`. New bytes are
initialized to 0.

Note that you can use `resize()` to shrink as well as grow an
`ArrayBuffer` --- it is permissible for `newLength` to be smaller than
the `ArrayBuffer`\'s current [`byteLength`](bytelength).




Examples
--------



### Using resize() 


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


  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-arraybuffer.prototype.resize]](https://tc39.es/ecma262/multipage/structured-data.html#sec-arraybuffer.prototype.resize)

  -------------------------------------------------------------------------------------------------------------------------------------


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

`resize`

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
-   [`ArrayBuffer.prototype.resizable`](resizable)
-   [`ArrayBuffer.prototype.maxByteLength`](maxbytelength)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/resize>

