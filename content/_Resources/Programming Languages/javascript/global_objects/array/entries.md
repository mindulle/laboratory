Array.prototype.entries()
=========================


The `entries()` method of [`Array`](../array) instances returns a new
*[array iterator](../iterator)* object that contains the key/value pairs
for each index in the array.



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


When used on [sparse
arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays),
the `entries()` method iterates empty slots as if they have the value
`undefined`.

The `entries()` method is [generic](../array#generic_array_methods). It
only expects the `this` value to have a `length` property and
integer-keyed properties.




Examples
--------



### Iterating with index and element 




[js]


```js
const a = ["a", "b", "c"];

for (const [index, element] of a.entries()) {
  console.log(index, element);
}

// 0 'a'
// 1 'b'
// 2 'c'
```





### Using a for\...of loop 




[js]


```js
const array = ["a", "b", "c"];
const arrayEntries = array.entries();

for (const element of arrayEntries) {
  console.log(element);
}

// [0, 'a']
// [1, 'b']
// [2, 'c']
```





### Iterating sparse arrays 


`entries()` will visit empty slots as if they are `undefined`.



[js]


```js
for (const element of [, "a"].entries()) {
  console.log(element);
}
// [0, undefined]
// [1, 'a']
```





### Calling entries() on non-array objects 


The `entries()` method reads the `length` property of `this` and then
accesses each property whose key is a nonnegative integer less than
`length`.



[js]


```js
const arrayLike = {
  length: 3,
  0: "a",
  1: "b",
  2: "c",
  3: "d", // ignored by entries() since length is 3
};
for (const entry of Array.prototype.entries.call(arrayLike)) {
  console.log(entry);
}
// [ 0, 'a' ]
// [ 1, 'b' ]
// [ 2, 'c' ]
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.entries]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.entries)

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

`entries`

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


-   [Polyfill of `Array.prototype.entries` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array.prototype.keys()`](keys)
-   [`Array.prototype.values()`](values)
-   [`Array.prototype[@@iterator]()`](@@iterator)
-   [`TypedArray.prototype.entries()`](../typedarray/entries)
-   [Iteration protocols](../../iteration_protocols)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/entries>

