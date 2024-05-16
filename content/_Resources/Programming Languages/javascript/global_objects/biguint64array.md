BigUint64Array
==============

 
The `BigUint64Array` typed array represents an array of 64-bit unsigned
integers in the platform byte order. If control over byte order is
needed, use [`DataView`](dataview) instead. The contents are initialized
to `0n`. Once established, you can reference elements in the array using
the object\'s methods, or using standard array index syntax (that is,
using bracket notation).

`BigUint64Array` is a subclass of the hidden [`TypedArray`](typedarray)
class.


 
Constructor
-----------

 

[`BigUint64Array()`](biguint64array/biguint64array)

:   Creates a new `BigUint64Array` object.



 
Static properties 
-----------------

 
*Also inherits static properties from its parent
[`TypedArray`](typedarray)*.

[`BigUint64Array.BYTES_PER_ELEMENT`](typedarray/bytes_per_element)

:   Returns a number value of the element size. `8` in the case of
    `BigUint64Array`.



 
Static methods 
--------------

 
*Inherits static methods from its parent [`TypedArray`](typedarray)*.



 
Instance properties 
-------------------

 
*Also inherits instance properties from its parent
[`TypedArray`](typedarray)*.

These properties are defined on `BigUint64Array.prototype` and shared by
all `BigUint64Array` instances.

[`BigUint64Array.prototype.BYTES_PER_ELEMENT`](typedarray/bytes_per_element)

:   Returns a number value of the element size. `8` in the case of a
    `BigUint64Array`.

[`BigUint64Array.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `BigUint64Array` instances, the initial value is the
    [`BigUint64Array`](biguint64array/biguint64array) constructor.



 
Instance methods 
----------------

 
*Inherits instance methods from its parent [`TypedArray`](typedarray)*.



 
Examples
--------


 
### Different ways to create a BigUint64Array 

 
 
 
[js]


```js
// From a length
const biguint64 = new BigUint64Array(2);
biguint64[0] = 42n;
console.log(biguint64[0]); // 42n
console.log(biguint64.length); // 2
console.log(biguint64.BYTES_PER_ELEMENT); // 8

// From an array
const x = new BigUint64Array([21n, 31n]);
console.log(x[1]); // 31n

// From another TypedArray
const y = new BigUint64Array(x);
console.log(y[0]); // 21n

// From an ArrayBuffer
const buffer = new ArrayBuffer(64);
const z = new BigUint64Array(buffer, 8, 4);
console.log(z.byteOffset); // 8

// From an iterable
const iterable = (function* () {
  yield* [1n, 2n, 3n];
})();
const biguint64FromIterable = new BigUint64Array(iterable);
console.log(biguint64FromIterable);
// BigUint64Array [1n, 2n, 3n]
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-typedarray-objects]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-typedarray-objects)

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

`BigUint64Array`

67

79

68

54

15

67

68

48

15

9.0

67

1.0

10.4.0

`BigUint64Array`

67

79

68

54

15

67

68

48

15

9.0

67

1.0

10.4.0

 
See also 
--------

 
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](typedarray)
-   [`ArrayBuffer`](arraybuffer)
-   [`DataView`](dataview)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigUint64Array>

