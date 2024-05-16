Float32Array
============

 
The `Float32Array` typed array represents an array of 32-bit floating
point numbers in the platform byte order. If control over byte order is
needed, use [`DataView`](dataview) instead. The contents are initialized
to `0`. Once established, you can reference elements in the array using
the object\'s methods, or using standard array index syntax (that is,
using bracket notation).

`Float32Array` is a subclass of the hidden [`TypedArray`](typedarray)
class.


 
Constructor
-----------

 

[`Float32Array()`](float32array/float32array)

:   Creates a new `Float32Array` object.



 
Static properties 
-----------------

 
*Also inherits static properties from its parent
[`TypedArray`](typedarray)*.

[`Float32Array.BYTES_PER_ELEMENT`](typedarray/bytes_per_element)

:   Returns a number value of the element size. `4` in the case of
    `Float32Array`.



 
Static methods 
--------------

 
*Inherits static methods from its parent [`TypedArray`](typedarray)*.



 
Instance properties 
-------------------

 
*Also inherits instance properties from its parent
[`TypedArray`](typedarray)*.

These properties are defined on `Float32Array.prototype` and shared by
all `Float32Array` instances.

[`Float32Array.prototype.BYTES_PER_ELEMENT`](typedarray/bytes_per_element)

:   Returns a number value of the element size. `4` in the case of a
    `Float32Array`.

[`Float32Array.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `Float32Array` instances, the initial value is the
    [`Float32Array`](float32array/float32array) constructor.



 
Instance methods 
----------------

 
*Inherits instance methods from its parent [`TypedArray`](typedarray)*.



 
Examples
--------


 
### Different ways to create a Float32Array 

 
 
 
[js]


```js
// From a length
const float32 = new Float32Array(2);
float32[0] = 42;
console.log(float32[0]); // 42
console.log(float32.length); // 2
console.log(float32.BYTES_PER_ELEMENT); // 4

// From an array
const x = new Float32Array([21, 31]);
console.log(x[1]); // 31

// From another TypedArray
const y = new Float32Array(x);
console.log(y[0]); // 21

// From an ArrayBuffer
const buffer = new ArrayBuffer(32);
const z = new Float32Array(buffer, 4, 4);
console.log(z.byteOffset); // 4

// From an iterable
const iterable = (function* () {
  yield* [1, 2, 3];
})();
const float32FromIterable = new Float32Array(iterable);
console.log(float32FromIterable);
// Float32Array [1, 2, 3]
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

`Float32Array`

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

`Float32Array`

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

 
-   [Polyfill of `Float32Array` in
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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array>

