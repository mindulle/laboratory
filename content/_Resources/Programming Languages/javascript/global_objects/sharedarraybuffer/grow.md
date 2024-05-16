SharedArrayBuffer.prototype.grow()
==================================

 
The `grow()` method of [`SharedArrayBuffer`](../sharedarraybuffer)
instances grows the `SharedArrayBuffer` to the specified size, in bytes.


 
Syntax
------

 
 
 
[js]


```js
grow(newLength)
```




 
### Parameters

 

[`newLength`](#newlength)

:   The new length, in bytes, to resize the `SharedArrayBuffer` to.



 
### Return value 

 
None ([`undefined`](../undefined)).



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if the `SharedArrayBuffer` is not growable.

[`RangeError`](../rangeerror)

:   Thrown if `newLength` is larger than the
    [`maxByteLength`](maxbytelength) of the `SharedArrayBuffer` or
    smaller than the [`byteLength`](bytelength).



 
Description
-----------

 
The `grow()` method grows a `SharedArrayBuffer` to the size specified by
the `newLength` parameter, provided that the `SharedArrayBuffer` is
[growable](growable) and the new size is less than or equal to the
[`maxByteLength`](maxbytelength) of the `SharedArrayBuffer`. New bytes
are initialized to 0.



 
Examples
--------


 
### Using grow() 

 
In this example, we create a 8-byte buffer that is growable to a max
length of 16 bytes, then check its [`growable`](growable) property,
growing it if `growable` returns `true`:

 
 
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

 
  ---------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-sharedarraybuffer.prototype.grow]](https://tc39.es/ecma262/multipage/structured-data.html#sec-sharedarraybuffer.prototype.grow)

  ---------------------------------------------------------------------------------------------------------------------------------------------


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

`grow`

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
-   [`SharedArrayBuffer.prototype.growable`](growable)
-   [`SharedArrayBuffer.prototype.maxByteLength`](maxbytelength)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer/grow>

