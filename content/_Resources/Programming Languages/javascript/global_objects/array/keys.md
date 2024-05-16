Array.prototype.keys()
======================


The `keys()` method of [`Array`](../array) instances returns a new
*[array iterator](../iterator)* object that contains the keys for each
index in the array.



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


When used on [sparse
arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays),
the `keys()` method iterates empty slots as if they have the value
`undefined`.

The `keys()` method is [generic](../array#generic_array_methods). It
only expects the `this` value to have a `length` property and
integer-keyed properties.




Examples
--------



### Using keys() on sparse arrays 


Unlike [`Object.keys()`](../object/keys), which only includes keys that
actually exist in the array, the `keys()` iterator doesn\'t ignore holes
representing missing properties.



[js]


```js
const arr = ["a", , "c"];
const sparseKeys = Object.keys(arr);
const denseKeys = [...arr.keys()];
console.log(sparseKeys); // ['0', '2']
console.log(denseKeys); // [0, 1, 2]
```





### Calling keys() on non-array objects 


The `keys()` method reads the `length` property of `this` and then
yields all integer indices between 0 and `length - 1`. No index access
actually happens.



[js]


```js
const arrayLike = {
  length: 3,
};
for (const entry of Array.prototype.keys.call(arrayLike)) {
  console.log(entry);
}
// 0
// 1
// 2
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.keys]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.keys)

  -------------------------------------------------------------------------------------------------------------------------


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

28

25

8

38

28

25

8

3.0

38

1.0

0.12.0


See also 
--------


-   [Polyfill of `Array.prototype.keys` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array.prototype.entries()`](entries)
-   [`Array.prototype.values()`](values)
-   [`Array.prototype[@@iterator]()`](@@iterator)
-   [`TypedArray.prototype.keys()`](../typedarray/keys)
-   [Iteration protocols](../../iteration_protocols)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/keys>

