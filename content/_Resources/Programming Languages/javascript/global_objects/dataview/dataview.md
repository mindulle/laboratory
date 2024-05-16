DataView() constructor
======================

 
The `DataView()` constructor creates [`DataView`](../dataview) objects.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new DataView(buffer)
new DataView(buffer, byteOffset)
new DataView(buffer, byteOffset, byteLength)
```


 
**Note:** `DataView()` can only be constructed with
[`new`](../../operators/new). Attempting to call it without `new` throws
a [`TypeError`](../typeerror).




 
### Parameters

 

[`buffer`](#buffer)

:   An existing [`ArrayBuffer`](../arraybuffer) or
    [`SharedArrayBuffer`](../sharedarraybuffer) to use as the storage
    backing the new `DataView` object.

[`byteOffset`](#byteoffset) [Optional]

:   The offset, in bytes, to the first byte in the above buffer for the
    new view to reference. If unspecified, the buffer view starts with
    the first byte.

[`byteLength`](#bytelength) [Optional]

:   The number of elements in the byte array. If unspecified, the
    view\'s length will match the buffer\'s length.



 
### Return value 

 
A new [`DataView`](../dataview) object representing the specified data
buffer.



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if the `byteOffset` or `byteLength` parameter values result
    in the view extending past the end of the buffer. In other words,
    `byteOffset + byteLength > buffer.byteLength`.



 
Examples
--------


 
### Using DataView 

 
 
 
[js]


```js
const buffer = new ArrayBuffer(16);
const view = new DataView(buffer, 0);

view.setInt16(1, 42);
view.getInt16(1); // 42
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-dataview-constructor]](https://tc39.es/ecma262/multipage/structured-data.html#sec-dataview-constructor)

  ---------------------------------------------------------------------------------------------------------------------


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

`DataView`

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

`new_required`

11

13

40

15

5.1

18

40

14

5

1.0

≤37

1.0

0.10.0

`sharedarraybuffer_support`

68

79

78

55

15.2

89

79

63

15.2

15.0

89

1.0

8.10.0

 
See also 
--------

 
-   [Polyfill of `DataView` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [`DataView`](../dataview)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView/DataView>

