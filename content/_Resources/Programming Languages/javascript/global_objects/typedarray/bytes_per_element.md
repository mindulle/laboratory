TypedArray.BYTES\_PER\_ELEMENT
==============================

 
The `TypedArray.BYTES_PER_ELEMENT` static data property represents the
size in bytes of each element in a typed array.


 
Try it 
------

 



 
Value
-----

 
A number whose value depends on the type of `TypedArray`.

 
Property attributes of `TypedArray.BYTES_PER_ELEMENT`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
`TypedArray` objects differ from each other in the number of bytes per
element and in the way the bytes are interpreted. The
`BYTES_PER_ELEMENT` constant contains the number of bytes each element
in the given `TypedArray` has.

The `BYTES_PER_ELEMENT` property is both an *instance property* and a
*static property*. It\'s available on both `TypedArray` subclass
constructors and on instances of those constructors.

As an instance property, `BYTES_PER_ELEMENT` is defined on the
constructor\'s `prototype`.

 
 
[js]


```js
console.log(Object.hasOwn(Int8Array.prototype, "BYTES_PER_ELEMENT")); // true
```




 
Examples
--------


 
### Using BYTES\_PER\_ELEMENT 

 
As a static property:

 
 
[js]


```js
Int8Array.BYTES_PER_ELEMENT; // 1
Uint8Array.BYTES_PER_ELEMENT; // 1
Uint8ClampedArray.BYTES_PER_ELEMENT; // 1
Int16Array.BYTES_PER_ELEMENT; // 2
Uint16Array.BYTES_PER_ELEMENT; // 2
Int32Array.BYTES_PER_ELEMENT; // 4
Uint32Array.BYTES_PER_ELEMENT; // 4
Float32Array.BYTES_PER_ELEMENT; // 4
Float64Array.BYTES_PER_ELEMENT; // 8
BigInt64Array.BYTES_PER_ELEMENT; // 8
BigUint64Array.BYTES_PER_ELEMENT; // 8
```


As an instance property:

 
 
[js]


```js
new Int8Array([]).BYTES_PER_ELEMENT; // 1
new Uint8Array([]).BYTES_PER_ELEMENT; // 1
new Uint8ClampedArray([]).BYTES_PER_ELEMENT; // 1
new Int16Array([]).BYTES_PER_ELEMENT; // 2
new Uint16Array([]).BYTES_PER_ELEMENT; // 2
new Int32Array([]).BYTES_PER_ELEMENT; // 4
new Uint32Array([]).BYTES_PER_ELEMENT; // 4
new Float32Array([]).BYTES_PER_ELEMENT; // 4
new Float64Array([]).BYTES_PER_ELEMENT; // 8
new BigInt64Array([]).BYTES_PER_ELEMENT; // 8
new BigUint64Array([]).BYTES_PER_ELEMENT; // 8
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-typedarray.bytes\_per\_element]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-typedarray.bytes_per_element)

  -------------------------------------------------------------------------------------------------------------------------------------------


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

`BYTES_PER_ELEMENT`

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

 
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/BYTES_PER_ELEMENT>

