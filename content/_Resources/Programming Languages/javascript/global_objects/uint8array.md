Uint8Array
==========

 
The `Uint8Array` typed array represents an array of 8-bit unsigned
integers. The contents are initialized to `0`. Once established, you can
reference elements in the array using the object\'s methods, or using
standard array index syntax (that is, using bracket notation).

`Uint8Array` is a subclass of the hidden [`TypedArray`](typedarray)
class.


 
Constructor
-----------

 

[`Uint8Array()`](uint8array/uint8array)

:   Creates a new `Uint8Array` object.



 
Static properties 
-----------------

 
*Also inherits static properties from its parent
[`TypedArray`](typedarray)*.

[`Uint8Array.BYTES_PER_ELEMENT`](typedarray/bytes_per_element)

:   Returns a number value of the element size. `1` in the case of
    `Uint8Array`.



 
Static methods 
--------------

 
*Inherits static methods from its parent [`TypedArray`](typedarray)*.



 
Instance properties 
-------------------

 
*Also inherits instance properties from its parent
[`TypedArray`](typedarray)*.

These properties are defined on `Uint8Array.prototype` and shared by all
`Uint8Array` instances.

[`Uint8Array.prototype.BYTES_PER_ELEMENT`](typedarray/bytes_per_element)

:   Returns a number value of the element size. `1` in the case of a
    `Uint8Array`.

[`Uint8Array.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `Uint8Array` instances, the initial value is the
    [`Uint8Array`](uint8array/uint8array) constructor.



 
Instance methods 
----------------

 
*Inherits instance methods from its parent [`TypedArray`](typedarray)*.



 
Examples
--------


 
### Different ways to create a Uint8Array 

 
 
 
[js]


```js
// From a length
const uint8 = new Uint8Array(2);
uint8[0] = 42;
console.log(uint8[0]); // 42
console.log(uint8.length); // 2
console.log(uint8.BYTES_PER_ELEMENT); // 1

// From an array
const x = new Uint8Array([21, 31]);
console.log(x[1]); // 31

// From another TypedArray
const y = new Uint8Array(x);
console.log(y[0]); // 21

// From an ArrayBuffer
const buffer = new ArrayBuffer(8);
const z = new Uint8Array(buffer, 1, 4);
console.log(z.byteOffset); // 1

// From an iterable
const iterable = (function* () {
  yield* [1, 2, 3];
})();
const uint8FromIterable = new Uint8Array(iterable);
console.log(uint8FromIterable);
// Uint8Array [1, 2, 3]
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

`Uint8Array`

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

`Uint8Array`

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

 
-   [Polyfill of `Uint8Array` in
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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array>

