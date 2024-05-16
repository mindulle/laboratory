Array.prototype.copyWithin()
============================


The `copyWithin()` method of [`Array`](../array) instances shallow
copies part of this array to another location in the same array and
returns this array without modifying its length.



Try it 
------






Syntax
------




[js]


```js
copyWithin(target, start)
copyWithin(target, start, end)
```





### Parameters



[`target`](#target)

:   Zero-based index at which to copy the sequence to, [converted to an
    integer](../number#integer_conversion). This corresponds to where
    the element at `start` will be copied to, and all elements between
    `start` and `end` are copied to succeeding indices.

    -   Negative index counts back from the end of the array --- if
        `target < 0`, `target + array.length` is used.
    -   If `target < -array.length`, `0` is used.
    -   If `target >= array.length`, nothing is copied.
    -   If `target` is positioned after `start` after normalization,
        copying only happens until the end of `array.length` (in other
        words, `copyWithin()` never extends the array).

[`start`](#start)

:   Zero-based index at which to start copying elements from, [converted
    to an integer](../number#integer_conversion).

    -   Negative index counts back from the end of the array --- if
        `start < 0`, `start + array.length` is used.
    -   If `start < -array.length`, `0` is used.
    -   If `start >= array.length`, nothing is copied.

[`end`](#end) [Optional]

:   Zero-based index at which to end copying elements from, [converted
    to an integer](../number#integer_conversion). `copyWithin()` copies
    up to but not including `end`.

    -   Negative index counts back from the end of the array --- if
        `end < 0`, `end + array.length` is used.
    -   If `end < -array.length`, `0` is used.
    -   If `end >= array.length` or `end` is omitted, `array.length` is
        used, causing all elements until the end to be copied.
    -   If `end` is positioned before or at `start` after normalization,
        nothing is copied.




### Return value 


The modified array.




Description
-----------


The `copyWithin()` method works like C and C++\'s `memmove`, and is a
high-performance method to shift the data of an [`Array`](../array).
This especially applies to the [`TypedArray`](../typedarray/copywithin)
method of the same name. The sequence is copied and pasted as one
operation; the pasted sequence will have the copied values even when the
copy and paste region overlap.

Because `undefined` becomes `0` when converted to an integer, omitting
the `start` parameter has the same effect as passing `0`, which copies
the entire array to the target position, equivalent to a right shift
where the right boundary is clipped off and the left boundary is
duplicated. This behavior may confuse readers of your code, so you
should explicitly pass `0` as `start` instead.



[js]


```js
console.log([1, 2, 3, 4, 5].copyWithin(2));
// [1, 2, 1, 2, 3]; move all elements to the right by 2 positions
```


The `copyWithin()` method is a [mutating
method](../array#copying_methods_and_mutating_methods). It does not
alter the length of `this`, but it will change the content of `this` and
create new properties or delete existing properties, if necessary.

The `copyWithin()` method preserves empty slots. If the region to be
copied from is
[sparse](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays),
the empty slots\' corresponding new indices are
[deleted](../../operators/delete) and also become empty slots.

The `copyWithin()` method is [generic](../array#generic_array_methods).
It only expects the `this` value to have a `length` property and
integer-keyed properties. Although strings are also array-like, this
method is not suitable to be applied on them, as strings are immutable.




Examples
--------



### Using copyWithin() 




[js]


```js
console.log([1, 2, 3, 4, 5].copyWithin(0, 3));
// [4, 5, 3, 4, 5]

console.log([1, 2, 3, 4, 5].copyWithin(0, 3, 4));
// [4, 2, 3, 4, 5]

console.log([1, 2, 3, 4, 5].copyWithin(-2, -3, -1));
// [1, 2, 3, 3, 4]
```





### Using copyWithin() on sparse arrays 


`copyWithin()` will propagate empty slots.



[js]


```js
console.log([1, , 3].copyWithin(2, 1, 2)); // [1, empty, empty]
```





### Calling copyWithin() on non-array objects 


The `copyWithin()` method reads the `length` property of `this` and then
manipulates the integer indices involved.



[js]


```js
const arrayLike = {
  length: 5,
  3: 1,
};
console.log(Array.prototype.copyWithin.call(arrayLike, 0, 3));
// { '0': 1, '3': 1, length: 5 }
console.log(Array.prototype.copyWithin.call(arrayLike, 3, 1));
// { '0': 1, length: 5 }
// The '3' property is deleted because the copied source is an empty slot
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.copywithin]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.copywithin)

  -------------------------------------------------------------------------------------------------------------------------------------


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

`copyWithin`

45

12

32

32

9

45

32

32

9

5.0

45

1.0

4.0.0


See also 
--------


-   [Polyfill of `Array.prototype.copyWithin` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`TypedArray.prototype.copyWithin()`](../typedarray/copywithin)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/copyWithin>

