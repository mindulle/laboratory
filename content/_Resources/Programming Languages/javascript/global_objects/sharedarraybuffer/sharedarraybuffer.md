SharedArrayBuffer() constructor
===============================

 
 
**Note:** The `SharedArrayBuffer` constructor may not always be globally
available unless certain [security
requirements](../sharedarraybuffer#security_requirements) are met.


The `SharedArrayBuffer()` constructor creates
[`SharedArrayBuffer`](../sharedarraybuffer) objects.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new SharedArrayBuffer(length)
new SharedArrayBuffer(length, options)
```


 
**Note:** `SharedArrayBuffer()` can only be constructed with
[`new`](../../operators/new). Attempting to call it without `new` throws
a [`TypeError`](../typeerror).




 
### Parameters

 

[`length`](#length)

:   The size, in bytes, of the array buffer to create.

[`options`](#options) [Optional]

:   An object, which can contain the following properties:

    [`maxByteLength`](#maxbytelength) [Optional]

    :   The maximum size, in bytes, that the shared array buffer can be
        resized to.



 
### Return value 

 
A new `SharedArrayBuffer` object of the specified size, with its
[`maxByteLength`](maxbytelength) property set to the specified
`maxByteLength` if one was specified. Its contents are initialized to 0.



 
Examples
--------


 
### Always use the new operator to create a SharedArrayBuffer 

 
`SharedArrayBuffer` constructors are required to be constructed with a
[`new`](../../operators/new) operator. Calling a `SharedArrayBuffer`
constructor as a function without `new` will throw a
[`TypeError`](../typeerror).

 
 
[js]


```js
const sab = SharedArrayBuffer(1024);
// TypeError: calling a builtin SharedArrayBuffer constructor
// without new is forbidden
```


 
 
[js]


```js
const sab = new SharedArrayBuffer(1024);
```




 
### Growing a growable SharedArrayBuffer 

 
In this example, we create an 8-byte buffer that is growable to a max
length of 16 bytes, then [`grow()`](grow) it to 12 bytes:

 
 
[js]


```js
const buffer = new SharedArrayBuffer(8, { maxByteLength: 16 });

buffer.grow(12);
```


 
**Note:** It is recommended that `maxByteLength` is set to the smallest
value possible for your use case. It should never exceed `1073741824`
(1GB), to reduce the risk of out-of-memory errors.




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-sharedarraybuffer-constructor]](https://tc39.es/ecma262/multipage/structured-data.html#sec-sharedarraybuffer-constructor)

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

`SharedArrayBuffer`

68

79

79

55

15.2

89

79

63

15.2

15.0

No

1.0

8.10.0

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

No

1.33

20.0.0

 
See also 
--------

 
-   [`Atomics`](../atomics)
-   [`ArrayBuffer`](../arraybuffer)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer/SharedArrayBuffer>

