TypedArray.prototype.values()
=============================

 
The `values()` method of [`TypedArray`](../typedarray) instances returns
a new *[array iterator](../iterator)* object that iterates the value of
each item in the typed array. This method has the same algorithm as
[`Array.prototype.values()`](../array/values).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
values()
```




 
### Parameters

 
None.



 
### Return value 

 
A new [iterable iterator object](../iterator).



 
Description
-----------

 
See [`Array.prototype.values()`](../array/values) for more details. This
method is not generic and can only be called on typed array instances.



 
Examples
--------


 
### Iteration using for\...of loop 

 
 
 
[js]


```js
const arr = new Uint8Array([10, 20, 30, 40, 50]);
const values = arr.values();
for (const n of values) {
  console.log(n);
}
```




 
### Alternative iteration 

 
 
 
[js]


```js
const arr = new Uint8Array([10, 20, 30, 40, 50]);
const values = arr.values();
console.log(values.next().value); // 10
console.log(values.next().value); // 20
console.log(values.next().value); // 30
console.log(values.next().value); // 40
console.log(values.next().value); // 50
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.values]](#)

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

`values`

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

 
-   [Polyfill of `TypedArray.prototype.values` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.entries()`](entries)
-   [`TypedArray.prototype.keys()`](keys)
-   [`TypedArray.prototype[@@iterator]()`](@@iterator)
-   [`Array.prototype.values()`](../array/values)
-   [Iteration protocols](../../iteration_protocols)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/values>

