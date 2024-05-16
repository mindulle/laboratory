Array.prototype.includes()
==========================


The `includes()` method of [`Array`](../array) instances determines
whether an array includes a certain value among its entries, returning
`true` or `false` as appropriate.



Try it 
------






Syntax
------




[js]


```js
includes(searchElement)
includes(searchElement, fromIndex)
```





### Parameters



[`searchElement`](#searchelement)

:   The value to search for.

[`fromIndex`](#fromindex) [Optional]

:   Zero-based index at which to start searching, [converted to an
    integer](../number#integer_conversion).

    -   Negative index counts back from the end of the array --- if
        `fromIndex < 0`, `fromIndex + array.length` is used. However,
        the array is still searched from front to back in this case.
    -   If `fromIndex < -array.length` or `fromIndex` is omitted, `0` is
        used, causing the entire array to be searched.
    -   If `fromIndex >= array.length`, the array is not searched and
        `false` is returned.




### Return value 


A boolean value which is `true` if the value `searchElement` is found
within the array (or the part of the array indicated by the index
`fromIndex`, if specified).




Description
-----------


The `includes()` method compares `searchElement` to elements of the
array using the
[SameValueZero](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness#same-value-zero_equality)
algorithm. Values of zero are all considered to be equal, regardless of
sign. (That is, `-0` is equal to `0`), but `false` is *not* considered
to be the same as `0`. [`NaN`](../nan) can be correctly searched for.

When used on [sparse
arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays),
the `includes()` method iterates empty slots as if they have the value
`undefined`.

The `includes()` method is [generic](../array#generic_array_methods). It
only expects the `this` value to have a `length` property and
integer-keyed properties.




Examples
--------



### Using includes() 




[js]


```js
[1, 2, 3].includes(2); // true
[1, 2, 3].includes(4); // false
[1, 2, 3].includes(3, 3); // false
[1, 2, 3].includes(3, -1); // true
[1, 2, NaN].includes(NaN); // true
["1", "2", "3"].includes(3); // false
```





### fromIndex is greater than or equal to the array length 


If `fromIndex` is greater than or equal to the length of the array,
`false` is returned. The array will not be searched.



[js]


```js
const arr = ["a", "b", "c"];

arr.includes("c", 3); // false
arr.includes("c", 100); // false
```





### Computed index is less than 0 


If `fromIndex` is negative, the computed index is calculated to be used
as a position in the array at which to begin searching for
`searchElement`. If the computed index is less than or equal to `0`, the
entire array will be searched.



[js]


```js
// array length is 3
// fromIndex is -100
// computed index is 3 + (-100) = -97

const arr = ["a", "b", "c"];

arr.includes("a", -100); // true
arr.includes("b", -100); // true
arr.includes("c", -100); // true
arr.includes("a", -2); // false
```





### Using includes() on sparse arrays 


You can search for `undefined` in a sparse array and get `true`.



[js]


```js
console.log([1, , 3].includes(undefined)); // true
```





### Calling includes() on non-array objects 


The `includes()` method reads the `length` property of `this` and then
accesses each property whose key is a nonnegative integer less than
`length`.



[js]


```js
const arrayLike = {
  length: 3,
  0: 2,
  1: 3,
  2: 4,
  3: 1, // ignored by includes() since length is 3
};
console.log(Array.prototype.includes.call(arrayLike, 2));
// true
console.log(Array.prototype.includes.call(arrayLike, 1));
// false
```




Specifications
--------------


  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.includes]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.includes)

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

`includes`

47

14

43

34

9

47

43

34

9

5.0

47

1.0

6.0.0


See also 
--------


-   [Polyfill of `Array.prototype.includes` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array.prototype.indexOf()`](indexof)
-   [`Array.prototype.find()`](find)
-   [`Array.prototype.findIndex()`](findindex)
-   [`TypedArray.prototype.includes()`](../typedarray/includes)
-   [`String.prototype.includes()`](../string/includes)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes>

