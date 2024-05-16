Array.prototype.toSorted()
==========================


The `toSorted()` method of [`Array`](../array) instances is the
[copying](../array#copying_methods_and_mutating_methods) version of the
[`sort()`](sort) method. It returns a new array with the elements sorted
in ascending order.



Syntax
------




[js]


```js
toSorted()
toSorted(compareFn)
```





### Parameters



[`compareFn`](#comparefn) [Optional]

:   Specifies a function that defines the sort order. If omitted, the
    array elements are converted to strings, then sorted according to
    each character\'s Unicode code point value.

    [`a`](#a)

    :   The first element for comparison.

    [`b`](#b)

    :   The second element for comparison.




### Return value 


A new array with the elements sorted in ascending order.




Description
-----------


See [`sort()`](sort) for more information on the `compareFn` parameter.

When used on [sparse
arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays),
the `toSorted()` method iterates empty slots as if they have the value
`undefined`.

The `toSorted()` method is [generic](../array#generic_array_methods). It
only expects the `this` value to have a `length` property and
integer-keyed properties.




Examples
--------



### Sorting an array 




[js]


```js
const months = ["Mar", "Jan", "Feb", "Dec"];
const sortedMonths = months.toSorted();
console.log(sortedMonths); // ['Dec', 'Feb', 'Jan', 'Mar']
console.log(months); // ['Mar', 'Jan', 'Feb', 'Dec']

const values = [1, 10, 21, 2];
const sortedValues = values.toSorted((a, b) => a - b);
console.log(sortedValues); // [1, 2, 10, 21]
console.log(values); // [1, 10, 21, 2]
```


For more usage examples, see [`sort()`](sort).




### Using toSorted() on sparse arrays 


Empty slots are sorted as if they have the value `undefined`. They are
always sorted to the end of the array and `compareFn` is not called for
them.



[js]


```js
console.log(["a", "c", , "b"].toSorted()); // ['a', 'b', 'c', undefined]
console.log([, undefined, "a", "b"].toSorted()); // ["a", "b", undefined, undefined]
```





### Calling toSorted() on non-array objects 


The `toSorted()` method reads the `length` property of `this`. It then
collects all existing integer-keyed properties in the range of `0` to
`length - 1`, sorts them, and writes them into a new array.



[js]


```js
const arrayLike = {
  length: 3,
  unrelated: "foo",
  0: 5,
  2: 4,
  3: 3, // ignored by toSorted() since length is 3
};
console.log(Array.prototype.toSorted.call(arrayLike));
// [4, 5, undefined]
```




Specifications
--------------


  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.tosorted]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.tosorted)

  ---------------------------------------------------------------------------------------------------------------------------------


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

`toSorted`

110

110

115

96

16

110

115

74

16

21.0

110

1.31

20.0.0


See also 
--------


-   [Polyfill of `Array.prototype.toSorted` in
    `core-js`](https://github.com/zloirock/core-js#change-array-by-copy)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array.prototype.sort()`](sort)
-   [`Array.prototype.toReversed()`](toreversed)
-   [`Array.prototype.toSpliced()`](tospliced)
-   [`Array.prototype.with()`](with)
-   [`TypedArray.prototype.toSorted()`](../typedarray/tosorted)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toSorted>

