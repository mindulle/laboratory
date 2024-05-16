Uint16Array
===========

 
The `Uint16Array` typed array represents an array of 16-bit unsigned
integers in the platform byte order. If control over byte order is
needed, use [`DataView`](dataview) instead. The contents are initialized
to `0`. Once established, you can reference elements in the array using
the object\'s methods, or using standard array index syntax (that is,
using bracket notation).

`Uint16Array` is a subclass of the hidden [`TypedArray`](typedarray)
class.


 
Constructor
-----------

 

[`Uint16Array()`](uint16array/uint16array)

:   Creates a new `Uint16Array` object.



 
Static properties 
-----------------

 
*Also inherits static properties from its parent
[`TypedArray`](typedarray)*.

[`Uint16Array.BYTES_PER_ELEMENT`](typedarray/bytes_per_element)

:   Returns a number value of the element size. `2` in the case of
    `Uint16Array`.



 
Static methods 
--------------

 
*Inherits static methods from its parent [`TypedArray`](typedarray)*.



 
Instance properties 
-------------------

 
*Also inherits instance properties from its parent
[`TypedArray`](typedarray)*.

These properties are defined on `Uint16Array.prototype` and shared by
all `Uint16Array` instances.

[`Uint16Array.prototype.BYTES_PER_ELEMENT`](typedarray/bytes_per_element)

:   Returns a number value of the element size. `2` in the case of a
    `Uint16Array`.

[`Uint16Array.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `Uint16Array` instances, the initial value is the
    [`Uint16Array`](uint16array/uint16array) constructor.



 
Instance methods 
----------------

 
*Inherits instance methods from its parent [`TypedArray`](typedarray)*.



 
Examples
--------


 
### Different ways to create a Uint16Array 

 
 
 
[js]


```js
// From a length
const uint16 = new Uint16Array(2);
uint16[0] = 42;
console.log(uint16[0]); // 42
console.log(uint16.length); // 2
console.log(uint16.BYTES_PER_ELEMENT); // 2

// From an array
const x = new Uint16Array([21, 31]);
console.log(x[1]); // 31

// From another TypedArray
const y = new Uint16Array(x);
console.log(y[0]); // 21

// From an ArrayBuffer
const buffer = new ArrayBuffer(16);
const z = new Uint16Array(buffer, 2, 4);
console.log(z.byteOffset); // 2

// From an iterable
const iterable = (function* () {
  yield* [1, 2, 3];
})();
const uint16FromIterable = new Uint16Array(iterable);
console.log(uint16FromIterable);
// Uint16Array [1, 2, 3]
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  table-49]](https://tc39.es/ecma262/multipage/indexed-collections.html#table-49)

  -----------------------------------------------------------------------------------------


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

`Uint16Array`

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

`Uint16Array`

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

 
See also 
--------

 
-   [Polyfill of `Uint16Array` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](typedarray)
-   [`ArrayBuffer`](arraybuffer)
-   [`DataView`](dataview)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint16Array>

