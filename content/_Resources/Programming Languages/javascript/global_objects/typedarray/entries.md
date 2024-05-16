TypedArray.prototype.entries()
==============================

 
The `entries()` method of [`TypedArray`](../typedarray) instances
returns a new *[array iterator](../iterator)* object that contains the
key/value pairs for each index in the typed array. This method has the
same algorithm as [`Array.prototype.entries()`](../array/entries).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
entries()
```




 
### Parameters

 
None.



 
### Return value 

 
A new [iterable iterator object](../iterator).



 
Description
-----------

 
See [`Array.prototype.entries()`](../array/entries) for more details.
This method is not generic and can only be called on typed array
instances.



 
Examples
--------


 
### Iteration using for\...of loop 

 
 
 
[js]


```js
const array = new Uint8Array([10, 20, 30, 40, 50]);
const arrayEntries = arr.entries();
for (const element of arrayEntries) {
  console.log(element);
}
```




 
### Alternative iteration 

 
 
 
[js]


```js
const array = new Uint8Array([10, 20, 30, 40, 50]);
const arrayEntries = arr.entries();

console.log(arrayEntries.next().value); // [0, 10]
console.log(arrayEntries.next().value); // [1, 20]
console.log(arrayEntries.next().value); // [2, 30]
console.log(arrayEntries.next().value); // [3, 40]
console.log(arrayEntries.next().value); // [4, 50]
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.entries]](#)

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

`entries`

45

12

37

32

9.1

45

37

32

9.3

5.0

45

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.entries` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.keys()`](keys)
-   [`TypedArray.prototype.values()`](values)
-   [`TypedArray.prototype[@@iterator]()`](@@iterator)
-   [`Array.prototype.entries()`](../array/entries)
-   [Iteration protocols](../../iteration_protocols)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/entries>

