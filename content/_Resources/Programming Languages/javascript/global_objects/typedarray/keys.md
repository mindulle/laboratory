TypedArray.prototype.keys()
===========================

 
The `keys()` method of [`TypedArray`](../typedarray) instances returns a
new *[array iterator](../iterator)* object that contains the keys for
each index in the typed array. This method has the same algorithm as
[`Array.prototype.keys()`](../array/keys).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
keys()
```




 
### Parameters

 
None.



 
### Return value 

 
A new [iterable iterator object](../iterator).



 
Description
-----------

 
See [`Array.prototype.keys()`](../array/keys) for more details. This
method is not generic and can only be called on typed array instances.



 
Examples
--------


 
### Iteration using for\...of loop 

 
 
 
[js]


```js
const arr = new Uint8Array([10, 20, 30, 40, 50]);
const arrKeys = arr.keys();
for (const n of arrKeys) {
  console.log(n);
}
```




 
### Alternative iteration 

 
 
 
[js]


```js
const arr = new Uint8Array([10, 20, 30, 40, 50]);
const arrKeys = arr.keys();
console.log(arrKeys.next().value); // 0
console.log(arrKeys.next().value); // 1
console.log(arrKeys.next().value); // 2
console.log(arrKeys.next().value); // 3
console.log(arrKeys.next().value); // 4
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.keys]](#)

  -----------------------------------------------------------------------


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

`keys`

38

12

37

25

10

38

37

25

10

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.keys` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.entries()`](entries)
-   [`TypedArray.prototype.values()`](values)
-   [`TypedArray.prototype[@@iterator]()`](@@iterator)
-   [`Array.prototype.keys()`](../array/keys)
-   [Iteration protocols](../../iteration_protocols)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/keys>

