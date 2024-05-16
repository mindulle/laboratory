ArrayBuffer.isView()
====================


The `ArrayBuffer.isView()` static method determines whether the passed
value is one of the `ArrayBuffer` views, such as [typed array
objects](../typedarray) or a [`DataView`](../dataview).



Try it 
------






Syntax
------




[js]


```js
ArrayBuffer.isView(value)
```





### Parameters



[`value`](#value)

:   The value to be checked.




### Return value 


`true` if the given argument is one of the
[`ArrayBuffer`](../arraybuffer) views; otherwise, `false`.




Examples
--------



### Using isView 




[js]


```js
ArrayBuffer.isView(); // false
ArrayBuffer.isView([]); // false
ArrayBuffer.isView({}); // false
ArrayBuffer.isView(null); // false
ArrayBuffer.isView(undefined); // false
ArrayBuffer.isView(new ArrayBuffer(10)); // false

ArrayBuffer.isView(new Uint8Array()); // true
ArrayBuffer.isView(new Float32Array()); // true
ArrayBuffer.isView(new Int8Array(10).subarray(0, 3)); // true

const buffer = new ArrayBuffer(2);
const dv = new DataView(buffer);
ArrayBuffer.isView(dv); // true
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-arraybuffer.isview]](https://tc39.es/ecma262/multipage/structured-data.html#sec-arraybuffer.isview)

  -----------------------------------------------------------------------------------------------------------------


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

`isView`

32

12

29

19

7

32

29

19

7

2.0

4.4.3

1.0

4.0.0


See also 
--------


-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/isView>

