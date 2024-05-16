Array.isArray()
===============


The `Array.isArray()` static method determines whether the passed value
is an [`Array`](../array).



Try it 
------






Syntax
------




[js]


```js
Array.isArray(value)
```





### Parameters



[`value`](#value)

:   The value to be checked.




### Return value 


`true` if `value` is an [`Array`](../array); otherwise, `false`. `false`
is always returned if `value` is a [`TypedArray`](../typedarray)
instance.




Description
-----------


`Array.isArray()` checks if the passed value is an [`Array`](../array).
It does not check the value\'s prototype chain, nor does it rely on the
`Array` constructor it is attached to. It returns `true` for any value
that was created using the array literal syntax or the `Array`
constructor. This makes it safe to use with cross-realm objects, where
the identity of the `Array` constructor is different and would therefore
cause [`instanceof Array`](../../operators/instanceof) to fail.

See the article [\"Determining with absolute accuracy whether or not a
JavaScript object is an
array\"](https://web.mit.edu/jwalden/www/isArray.html) for more details.

`Array.isArray()` also rejects objects with `Array.prototype` in its
prototype chain but aren\'t actual arrays, which `instanceof Array`
would accept.




Examples
--------



### Using Array.isArray() 




[js]


```js
// all following calls return true
Array.isArray([]);
Array.isArray([1]);
Array.isArray(new Array());
Array.isArray(new Array("a", "b", "c", "d"));
Array.isArray(new Array(3));
// Little known fact: Array.prototype itself is an array:
Array.isArray(Array.prototype);

// all following calls return false
Array.isArray();
Array.isArray({});
Array.isArray(null);
Array.isArray(undefined);
Array.isArray(17);
Array.isArray("Array");
Array.isArray(true);
Array.isArray(false);
Array.isArray(new Uint8Array(32));
// This is not an array, because it was not created using the
// array literal syntax or the Array constructor
Array.isArray({ __proto__: Array.prototype });
```





### instanceof vs. Array.isArray() 


When checking for `Array` instance, `Array.isArray()` is preferred over
`instanceof` because it works across realms.



[js]


```js
const iframe = document.createElement("iframe");
document.body.appendChild(iframe);
const xArray = window.frames[window.frames.length - 1].Array;
const arr = new xArray(1, 2, 3); // [1, 2, 3]

// Correctly checking for Array
Array.isArray(arr); // true
// The prototype of arr is xArray.prototype, which is a
// different object from Array.prototype
arr instanceof Array; // false
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.isarray]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.isarray)

  -----------------------------------------------------------------------------------------------------------


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

`isArray`

4

12

4

10.5

5

18

4

14

5

1.0

4.4

1.0

0.10.0


See also 
--------


-   [Polyfill of `Array.isArray` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray>

