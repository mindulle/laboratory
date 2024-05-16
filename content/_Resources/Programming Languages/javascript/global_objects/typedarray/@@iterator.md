TypedArray.prototype\[@\@iterator\]()
=====================================

 
The `[@@iterator]()` method of [`TypedArray`](../typedarray) instances
implements the [iterable protocol](../../iteration_protocols) and allows
typed arrays to be consumed by most syntaxes expecting iterables, such
as the [spread syntax](../../operators/spread_syntax) and
[`for...of`](../../statements/for...of) loops. It returns an [array
iterator object](../iterator) that yields the value of each index in the
typed array.

The initial value of this property is the same function object as the
initial value of the [`TypedArray.prototype.values`](values) property.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
typedArray[Symbol.iterator]()
```




 
### Parameters

 
None.



 
### Return value 

 
The same return value as [`TypedArray.prototype.values()`](values): a
new [iterable iterator object](../iterator) that yields the value of
each index in the typed array.



 
Examples
--------


 
### Iteration using for\...of loop 

 
Note that you seldom need to call this method directly. The existence of
the `@@iterator` method makes typed arrays
[iterable](../../iteration_protocols#the_iterable_protocol), and
iterating syntaxes like the `for...of` loop automatically call this
method to obtain the iterator to loop over.

 
 
[js]


```js
const arr = new Uint8Array([10, 20, 30, 40, 50]);
for (const n of arr) {
  console.log(n);
}
```




 
### Manually hand-rolling the iterator 

 
You may still manually call the `next()` method of the returned iterator
object to achieve maximum control over the iteration process.

 
 
[js]


```js
const arr = new Uint8Array([10, 20, 30, 40, 50]);
const arrIter = arr[Symbol.iterator]();
console.log(arrIter.next().value); // 10
console.log(arrIter.next().value); // 20
console.log(arrIter.next().value); // 30
console.log(arrIter.next().value); // 40
console.log(arrIter.next().value); // 50
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype-@\@iterator]](#)

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

`@@iterator`

38

12

36

27--36A placeholder property named `@@iterator` is used.

17--27A placeholder property named `iterator` is used.

25

10

38

36

27--36A placeholder property named `@@iterator` is used.

17--27A placeholder property named `iterator` is used.

25

10

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype[@@iterator]` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.entries()`](entries)
-   [`TypedArray.prototype.keys()`](keys)
-   [`TypedArray.prototype.values()`](values)
-   [`Symbol.iterator`](../symbol/iterator)
-   [Iteration protocols](../../iteration_protocols)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/@@iterator>

