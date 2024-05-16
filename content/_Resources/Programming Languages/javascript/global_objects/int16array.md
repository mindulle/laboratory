Int16Array
==========

 
The `Int16Array` typed array represents an array of 16-bit signed
integers in the platform byte order. If control over byte order is
needed, use [`DataView`](dataview) instead. The contents are initialized
to `0`. Once established, you can reference elements in the array using
the object\'s methods, or using standard array index syntax (that is,
using bracket notation).

`Int16Array` is a subclass of the hidden [`TypedArray`](typedarray)
class.


 
Constructor
-----------

 

[`Int16Array()`](int16array/int16array)

:   Creates a new `Int16Array` object.



 
Static properties 
-----------------

 
*Also inherits static properties from its parent
[`TypedArray`](typedarray)*.

[`Int16Array.BYTES_PER_ELEMENT`](typedarray/bytes_per_element)

:   Returns a number value of the element size. `2` in the case of
    `Int16Array`.



 
Static methods 
--------------

 
*Inherits static methods from its parent [`TypedArray`](typedarray)*.



 
Instance properties 
-------------------

 
*Also inherits instance properties from its parent
[`TypedArray`](typedarray)*.

These properties are defined on `Int16Array.prototype` and shared by all
`Int16Array` instances.

[`Int16Array.prototype.BYTES_PER_ELEMENT`](typedarray/bytes_per_element)

:   Returns a number value of the element size. `2` in the case of a
    `Int16Array`.

[`Int16Array.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `Int16Array` instances, the initial value is the
    [`Int16Array`](int16array/int16array) constructor.



 
Instance methods 
----------------

 
*Inherits instance methods from its parent [`TypedArray`](typedarray)*.



 
Examples
--------


 
### Different ways to create an Int16Array 

 
 
 
[js]


```js
// From a length
const int16 = new Int16Array(2);
int16[0] = 42;
console.log(int16[0]); // 42
console.log(int16.length); // 2
console.log(int16.BYTES_PER_ELEMENT); // 2

// From an array
const x = new Int16Array([21, 31]);
console.log(x[1]); // 31

// From another TypedArray
const y = new Int16Array(x);
console.log(y[0]); // 21

// From an ArrayBuffer
const buffer = new ArrayBuffer(16);
const z = new Int16Array(buffer, 2, 4);
console.log(z.byteOffset); // 2

// From an iterable
const iterable = (function* () {
  yield* [1, 2, 3];
})();
const int16FromIterable = new Int16Array(iterable);
console.log(int16FromIterable);
// Int16Array [1, 2, 3]
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

`Int16Array`

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

`Int16Array`

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

 
-   [Polyfill of `Int16Array` in
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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int16Array>

