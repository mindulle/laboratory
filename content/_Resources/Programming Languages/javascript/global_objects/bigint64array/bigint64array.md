BigInt64Array() constructor
===========================


The `BigInt64Array()` constructor creates
[`BigInt64Array`](../bigint64array) objects. The contents are
initialized to `0n`.



Syntax
------




[js]


```js
new BigInt64Array()
new BigInt64Array(length)
new BigInt64Array(typedArray)
new BigInt64Array(object)

new BigInt64Array(buffer)
new BigInt64Array(buffer, byteOffset)
new BigInt64Array(buffer, byteOffset, length)
```


 
**Note:** `BigInt64Array()` can only be constructed with
[`new`](../../operators/new). Attempting to call it without `new` throws
a [`TypeError`](../typeerror).





### Parameters


See [`TypedArray`](../typedarray#parameters).




### Exceptions


See [`TypedArray`](../typedarray#exceptions).




Examples
--------



### Different ways to create a BigInt64Array 




[js]


```js
// From a length
const bigint64 = new BigInt64Array(2);
bigint64[0] = 42n;
console.log(bigint64[0]); // 42n
console.log(bigint64.length); // 2
console.log(bigint64.BYTES_PER_ELEMENT); // 8

// From an array
const x = new BigInt64Array([21n, 31n]);
console.log(x[1]); // 31n

// From another TypedArray
const y = new BigInt64Array(x);
console.log(y[0]); // 21n

// From an ArrayBuffer
const buffer = new ArrayBuffer(64);
const z = new BigInt64Array(buffer, 8, 4);
console.log(z.byteOffset); // 8

// From an iterable
const iterable = (function* () {
  yield* [1n, 2n, 3n];
})();
const bigint64FromIterable = new BigInt64Array(iterable);
console.log(bigint64FromIterable);
// BigInt64Array [1n, 2n, 3n]
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

`BigInt64Array`

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
-   [`TypedArray`](../typedarray)
-   [`ArrayBuffer`](../arraybuffer)
-   [`DataView`](../dataview)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt64Array/BigInt64Array>

