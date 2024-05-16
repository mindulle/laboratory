Array.prototype.toSpliced()
===========================


The `toSpliced()` method of [`Array`](../array) instances is the
[copying](../array#copying_methods_and_mutating_methods) version of the
[`splice()`](splice) method. It returns a new array with some elements
removed and/or replaced at a given index.



Syntax
------




[js]


```js
toSpliced(start)
toSpliced(start, deleteCount)
toSpliced(start, deleteCount, item1)
toSpliced(start, deleteCount, item1, item2)
toSpliced(start, deleteCount, item1, item2, /* …, */ itemN)
```





### Parameters



[`start`](#start)

:   Zero-based index at which to start changing the array, [converted to
    an integer](../number#integer_conversion).

    -   Negative index counts back from the end of the array --- if
        `start < 0`, `start + array.length` is used.
    -   If `start < -array.length` or `start` is omitted, `0` is used.
    -   If `start >= array.length`, no element will be deleted, but the
        method will behave as an adding function, adding as many
        elements as provided.

[`deleteCount`](#deletecount) [Optional]

:   An integer indicating the number of elements in the array to remove
    from `start`.

    If `deleteCount` is omitted, or if its value is greater than or
    equal to the number of elements after the position specified by
    `start`, then all the elements from `start` to the end of the array
    will be deleted. However, if you wish to pass any `itemN` parameter,
    you should pass `Infinity` as `deleteCount` to delete all elements
    after `start`, because an explicit `undefined` gets
    [converted](../number#integer_conversion) to `0`.

    If `deleteCount` is `0` or negative, no elements are removed. In
    this case, you should specify at least one new element (see below).

[`item1`](#item1), ..., `itemN` [Optional]

:   The elements to add to the array, beginning from `start`.

    If you do not specify any elements, `toSpliced()` will only remove
    elements from the array.




### Return value 


A new array that consists of all elements before `start`, `item1`,
`item2`, ..., `itemN`, and all elements after `start + deleteCount`.




Description
-----------


The `toSpliced()` method, like `splice()`, does multiple things at once:
it removes the given number of elements from the array, starting at a
given index, and then inserts the given elements at the same index.
However, it returns a new array instead of modifying the original array.
The deleted elements therefore are not returned from this method.

The `toSpliced()` method never produces a [sparse
array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays).
If the source array is sparse, the empty slots will be replaced with
`undefined` in the new array.

The `toSpliced()` method is [generic](../array#generic_array_methods).
It only expects the `this` value to have a `length` property and
integer-keyed properties.




Examples
--------



### Deleting, adding, and replacing elements 


You can use `toSpliced()` to delete, add, and replace elements in an
array and create a new array more efficiently than using `slice()` and
`concat()`.



[js]


```js
const months = ["Jan", "Mar", "Apr", "May"];

// Inserting an element at index 1
const months2 = months.toSpliced(1, 0, "Feb");
console.log(months2); // ["Jan", "Feb", "Mar", "Apr", "May"]

// Deleting two elements starting from index 2
const months3 = months2.toSpliced(2, 2);
console.log(months3); // ["Jan", "Feb", "May"]

// Replacing one element at index 1 with two new elements
const months4 = months3.toSpliced(1, 1, "Feb", "Mar");
console.log(months4); // ["Jan", "Feb", "Mar", "May"]

// Original array is not modified
console.log(months); // ["Jan", "Mar", "Apr", "May"]
```





### Using toSpliced() on sparse arrays 


The `toSpliced()` method always creates a dense array.



[js]


```js
const arr = [1, , 3, 4, , 6];
console.log(arr.toSpliced(1, 2)); // [1, 4, undefined, 6]
```





### Calling toSpliced() on non-array objects 


The `toSpliced()` method reads the `length` property of `this`. It then
reads the integer-keyed properties needed and writes them into the new
array.



[js]


```js
const arrayLike = {
  length: 3,
  unrelated: "foo",
  0: 5,
  2: 4,
};
console.log(Array.prototype.toSpliced.call(arrayLike, 0, 1, 2, 3));
// [2, 3, undefined, 4]
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.tospliced]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.tospliced)

  -----------------------------------------------------------------------------------------------------------------------------------


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

`toSpliced`

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


-   [Polyfill of `Array.prototype.toSpliced` in
    `core-js`](https://github.com/zloirock/core-js#change-array-by-copy)
-   [`Array.prototype.splice()`](splice)
-   [`Array.prototype.toReversed()`](toreversed)
-   [`Array.prototype.toSorted()`](tosorted)
-   [`Array.prototype.with()`](with)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toSpliced>

