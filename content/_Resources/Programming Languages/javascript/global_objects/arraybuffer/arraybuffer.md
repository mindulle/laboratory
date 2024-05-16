ArrayBuffer() constructor
=========================


The `ArrayBuffer()` constructor creates [`ArrayBuffer`](../arraybuffer)
objects.



Try it 
------






Syntax
------




[js]


```js
new ArrayBuffer(length)
new ArrayBuffer(length, options)
```


 
**Note:** `ArrayBuffer()` can only be constructed with
[`new`](../../operators/new). Attempting to call it without `new` throws
a [`TypeError`](../typeerror).





### Parameters



[`length`](#length)

:   The size, in bytes, of the array buffer to create.

[`options`](#options) [Optional]

:   An object, which can contain the following properties:

    [`maxByteLength`](#maxbytelength) [Optional]

    :   The maximum size, in bytes, that the array buffer can be resized
        to.




### Return value 


A new `ArrayBuffer` object of the specified size, with its
[`maxByteLength`](maxbytelength) property set to the specified
`maxByteLength` if one was specified. Its contents are initialized to 0.




### Exceptions



[`RangeError`](../rangeerror)

:   Thrown in one of the following cases:

    -   `length` or `maxByteLength` is larger than
        [`Number.MAX_SAFE_INTEGER`](../number/max_safe_integer) (≥
        2^53^) or negative.
    -   `length` is larger than `maxByteLength`.




Examples
--------



### Creating an ArrayBuffer 


In this example, we create a 8-byte buffer with a
[`Int32Array`](../int32array) view referring to the buffer:



[js]


```js
const buffer = new ArrayBuffer(8);
const view = new Int32Array(buffer);
```





### Creating a resizable ArrayBuffer 


In this example, we create a 8-byte buffer that is resizable to a max
length of 16 bytes, then [`resize()`](resize) it to 12 bytes:



[js]


```js
const buffer = new ArrayBuffer(8, { maxByteLength: 16 });

buffer.resize(12);
```


 
**Note:** It is recommended that `maxByteLength` is set to the smallest
value possible for your use case. It should never exceed `1073741824`
(1GB) to reduce the risk of out-of-memory errors.




Specifications
--------------


  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-arraybuffer-constructor]](https://tc39.es/ecma262/multipage/structured-data.html#sec-arraybuffer-constructor)

  ---------------------------------------------------------------------------------------------------------------------------


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

`ArrayBuffer`

7

12

4

11.6

5.1

18

4

12

4.2

1.0

4

1.0

0.10.0

`maxByteLength_option`

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

`new_required`

7

14

44

15

5.1

18

44

14

5

1.0

≤37

1.0

0.12.0


See also 
--------


-   [Polyfill of `ArrayBuffer` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`SharedArrayBuffer`](../sharedarraybuffer)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/ArrayBuffer>

