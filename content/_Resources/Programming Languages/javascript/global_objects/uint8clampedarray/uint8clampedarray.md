Uint8ClampedArray() constructor
===============================

 
The `Uint8ClampedArray()` constructor creates
[`Uint8ClampedArray`](../uint8clampedarray) objects. The contents are
initialized to `0`.


 
Syntax
------

 
 
 
[js]


```js
new Uint8ClampedArray()
new Uint8ClampedArray(length)
new Uint8ClampedArray(typedArray)
new Uint8ClampedArray(object)

new Uint8ClampedArray(buffer)
new Uint8ClampedArray(buffer, byteOffset)
new Uint8ClampedArray(buffer, byteOffset, length)
```


 
**Note:** `Uint8ClampedArray()` can only be constructed with
[`new`](../../operators/new). Attempting to call it without `new` throws
a [`TypeError`](../typeerror).




 
### Parameters

 
See [`TypedArray`](../typedarray#parameters).



 
### Exceptions

 
See [`TypedArray`](../typedarray#exceptions).



 
Examples
--------


 
### Different ways to create a Uint8ClampedArray 

 
 
 
[js]


```js
// From a length
const uint8c = new Uint8ClampedArray(2);
uint8c[0] = 42;
uint8c[1] = 1337;
console.log(uint8c[0]); // 42
console.log(uint8c[1]); // 255 (clamped)
console.log(uint8c.length); // 2
console.log(uint8c.BYTES_PER_ELEMENT); // 1

// From an array
const x = new Uint8ClampedArray([21, 31]);
console.log(x[1]); // 31

// From another TypedArray
const y = new Uint8ClampedArray(x);
console.log(y[0]); // 21

// From an ArrayBuffer
const buffer = new ArrayBuffer(8);
const z = new Uint8ClampedArray(buffer, 1, 4);
console.log(z.byteOffset); // 1

// From an iterable
const iterable = (function* () {
  yield* [1, 2, 3];
})();
const uint8cFromIterable = new Uint8ClampedArray(iterable);
console.log(uint8cFromIterable);
// Uint8ClampedArray [1, 2, 3]
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-typedarray-constructors]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-typedarray-constructors)

  -------------------------------------------------------------------------------------------------------------------------------


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

`Uint8ClampedArray`

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

`constructor_without_parameters`

7

12

55

11.6

5.1

18

55

12

5

1.0

≤37

1.0

0.10.0

`iterable_allowed`

39

14

52

26

10

39

52

26

10

4.0

39

1.0

4.0.0

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

 
-   [Polyfill of `Uint8ClampedArray` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`ArrayBuffer`](../arraybuffer)
-   [`DataView`](../dataview)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8ClampedArray/Uint8ClampedArray>

