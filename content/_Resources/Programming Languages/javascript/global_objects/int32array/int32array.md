Int32Array() constructor
========================

 
The `Int32Array()` constructor creates [`Int32Array`](../int32array)
objects. The contents are initialized to `0`.


 
Syntax
------

 
 
 
[js]


```js
new Int32Array()
new Int32Array(length)
new Int32Array(typedArray)
new Int32Array(object)

new Int32Array(buffer)
new Int32Array(buffer, byteOffset)
new Int32Array(buffer, byteOffset, length)
```


 
**Note:** `Int32Array()` can only be constructed with
[`new`](../../operators/new). Attempting to call it without `new` throws
a [`TypeError`](../typeerror).




 
### Parameters

 
See [`TypedArray`](../typedarray#parameters).



 
### Exceptions

 
See [`TypedArray`](../typedarray#exceptions).



 
Examples
--------


 
### Different ways to create an Int32Array 

 
 
 
[js]


```js
// From a length
const int32 = new Int32Array(2);
int32[0] = 42;
console.log(int32[0]); // 42
console.log(int32.length); // 2
console.log(int32.BYTES_PER_ELEMENT); // 4

// From an array
const x = new Int32Array([21, 31]);
console.log(x[1]); // 31

// From another TypedArray
const y = new Int32Array(x);
console.log(y[0]); // 21

// From an ArrayBuffer
const buffer = new ArrayBuffer(32);
const z = new Int32Array(buffer, 4, 4);
console.log(z.byteOffset); // 4

// From an iterable
const iterable = (function* () {
  yield* [1, 2, 3];
})();
const int32FromIterable = new Int32Array(iterable);
console.log(int32FromIterable);
// Int32Array [1, 2, 3]
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

`Int32Array`

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

 
-   [Polyfill of `Int32Array` in
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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array/Int32Array>

