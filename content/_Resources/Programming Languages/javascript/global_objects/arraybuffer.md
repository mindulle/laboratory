ArrayBuffer
===========


The `ArrayBuffer` object is used to represent a generic raw binary data
buffer.

It is an array of bytes, often referred to in other languages as a
\"byte array\". You cannot directly manipulate the contents of an
`ArrayBuffer`; instead, you create one of the [typed array
objects](typedarray) or a [`DataView`](dataview) object which represents
the buffer in a specific format, and use that to read and write the
contents of the buffer.

The [`ArrayBuffer()`](arraybuffer/arraybuffer) constructor creates a new
`ArrayBuffer` of the given length in bytes. You can also get an array
buffer from existing data, for example, from a
[Base64](https://developer.mozilla.org/en-US/docs/Glossary/Base64)
string or [from a local
file](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsArrayBuffer).

`ArrayBuffer` is a [transferable
object](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Transferable_objects).



Description
-----------



### Resizing ArrayBuffers 


`ArrayBuffer` objects can be made resizable by including the
`maxByteLength` option when calling the
[`ArrayBuffer()`](arraybuffer/arraybuffer) constructor. You can query
whether an `ArrayBuffer` is resizable and what its maximum size is by
accessing its [`resizable`](arraybuffer/resizable) and
[`maxByteLength`](arraybuffer/maxbytelength) properties, respectively.
You can assign a new size to a resizable `ArrayBuffer` with a
[`resize()`](arraybuffer/resize) call. New bytes are initialized to 0.

These features make resizing `ArrayBuffer`s more efficient ---
otherwise, you have to make a copy of the buffer with a new size. It
also gives JavaScript parity with WebAssembly in this regard (Wasm
linear memory can be resized with
[`WebAssembly.Memory.prototype.grow()`](https://developer.mozilla.org/en-US/docs/WebAssembly/JavaScript_interface/Memory/grow)).




### Transferring ArrayBuffers 


`ArrayBuffer` objects can be transferred between different execution
contexts, like [Web
Workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)
or [Service
Workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API),
using the [structured clone
algorithm](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Structured_clone_algorithm).
This is done by passing the `ArrayBuffer` as a [transferable
object](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Transferable_objects)
in a call to
[`Worker.postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/postMessage)
or
[`ServiceWorker.postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker/postMessage).
In pure JavaScript, you can also transfer the ownership of memory from
one `ArrayBuffer` to another using its
[`transfer()`](arraybuffer/transfer) or
[`transferToFixedLength()`](arraybuffer/transfertofixedlength) method.

When an `ArrayBuffer` is transferred, its original copy becomes
*detached* --- this means it is no longer usable. At any moment, there
will only be one copy of the `ArrayBuffer` that actually has access to
the underlying memory. Detached buffers have the following behaviors:

-   [`byteLength`](arraybuffer/bytelength) becomes 0 (in both the buffer
    and the associated typed array views).
-   Methods, such as [`resize()`](arraybuffer/resize) and
    [`slice()`](arraybuffer/slice), throw a [`TypeError`](typeerror)
    when invoked. The associated typed array views\' methods also throw
    a `TypeError`.

You can check whether an `ArrayBuffer` is detached by its
[`detached`](arraybuffer/detached) property.




Constructor
-----------



[`ArrayBuffer()`](arraybuffer/arraybuffer)

:   Creates a new `ArrayBuffer` object.




Static properties 
-----------------



[`ArrayBuffer[@@species]`](arraybuffer/@@species)

:   The constructor function that is used to create derived objects.




Static methods 
--------------



[`ArrayBuffer.isView()`](arraybuffer/isview)

:   Returns `true` if `arg` is one of the ArrayBuffer views, such as
    [typed array objects](typedarray) or a [`DataView`](dataview).
    Returns `false` otherwise.




Instance properties 
-------------------


These properties are defined on `ArrayBuffer.prototype` and shared by
all `ArrayBuffer` instances.

[`ArrayBuffer.prototype.byteLength`](arraybuffer/bytelength)

:   The size, in bytes, of the `ArrayBuffer`. This is established when
    the array is constructed and can only be changed using the
    [`ArrayBuffer.prototype.resize()`](arraybuffer/resize) method if the
    `ArrayBuffer` is resizable.

[`ArrayBuffer.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `ArrayBuffer` instances, the initial value is the
    [`ArrayBuffer`](arraybuffer/arraybuffer) constructor.

[`ArrayBuffer.prototype.detached`](arraybuffer/detached)

:   Read-only. Returns `true` if the `ArrayBuffer` has been detached
    (transferred), or `false` if not.

[`ArrayBuffer.prototype.maxByteLength`](arraybuffer/maxbytelength)

:   The read-only maximum length, in bytes, that the `ArrayBuffer` can
    be resized to. This is established when the array is constructed and
    cannot be changed.

[`ArrayBuffer.prototype.resizable`](arraybuffer/resizable)

:   Read-only. Returns `true` if the `ArrayBuffer` can be resized, or
    `false` if not.

[`ArrayBuffer.prototype[@@toStringTag]`](#arraybuffer.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"ArrayBuffer"`. This property is used in
    [`Object.prototype.toString()`](object/tostring).




Instance methods 
----------------



[`ArrayBuffer.prototype.resize()`](arraybuffer/resize)

:   Resizes the `ArrayBuffer` to the specified size, in bytes.

[`ArrayBuffer.prototype.slice()`](arraybuffer/slice)

:   Returns a new `ArrayBuffer` whose contents are a copy of this
    `ArrayBuffer`\'s bytes from `begin` (inclusive) up to `end`
    (exclusive). If either `begin` or `end` is negative, it refers to an
    index from the end of the array, as opposed to from the beginning.

[`ArrayBuffer.prototype.transfer()`](arraybuffer/transfer)

:   Creates a new `ArrayBuffer` with the same byte content as this
    buffer, then detaches this buffer.

[`ArrayBuffer.prototype.transferToFixedLength()`](arraybuffer/transfertofixedlength)

:   Creates a new non-resizable `ArrayBuffer` with the same byte content
    as this buffer, then detaches this buffer.




Examples
--------



### Creating an ArrayBuffer 


In this example, we create a 8-byte buffer with a
[`Int32Array`](int32array) view referring to the buffer:



[js]


```js
const buffer = new ArrayBuffer(8);
const view = new Int32Array(buffer);
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-arraybuffer-objects]](https://tc39.es/ecma262/multipage/structured-data.html#sec-arraybuffer-objects)

  -------------------------------------------------------------------------------------------------------------------


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

`@@species`

51

13

48

38

10

51

48

41

10

5.0

51

1.0

6.5.0

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

`byteLength`

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

`detached`

114

114

122

100

preview

114

122

76

No

23.0

114

No

No

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

`maxByteLength`

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

`slice`

17

12

12The non-standard `ArrayBuffer.slice()` method has been removed in
Firefox 53 (but the standardized version `ArrayBuffer.prototype.slice()`
is kept.

12.1

5.1

18

14The non-standard `ArrayBuffer.slice()` method has been removed in
Firefox 53 (but the standardized version `ArrayBuffer.prototype.slice()`
is kept.

12.1

6

1.0

4.4

1.0

0.12.0

`transfer`

114

114

122

100

preview

114

122

76

No

23.0

114

No

No

`transferToFixedLength`

114

114

122

100

preview

114

122

76

No

23.0

114

No

No


See also 
--------


-   [Polyfill of `ArrayBuffer` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`SharedArrayBuffer`](sharedarraybuffer)
-   [RangeError: invalid array length](../errors/invalid_array_length)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer>

