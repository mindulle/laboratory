Array.prototype.reverse()
=========================


The `reverse()` method of [`Array`](../array) instances reverses an
array *[in place](https://en.wikipedia.org/wiki/In-place_algorithm)* and
returns the reference to the same array, the first array element now
becoming the last, and the last array element becoming the first. In
other words, elements order in the array will be turned towards the
direction opposite to that previously stated.

To reverse the elements in an array without mutating the original array,
use [`toReversed()`](toreversed).



Try it 
------






Syntax
------




[js]


```js
reverse()
```





### Parameters


None.




### Return value 


The reference to the original array, now reversed. Note that the array
is reversed *[in
place](https://en.wikipedia.org/wiki/In-place_algorithm)*, and no copy
is made.




Description
-----------


The `reverse()` method transposes the elements of the calling array
object in place, mutating the array, and returning a reference to the
array.

The `reverse()` method preserves empty slots. If the source array is
[sparse](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays),
the empty slots\' corresponding new indices are
[deleted](../../operators/delete) and also become empty slots.

The `reverse()` method is [generic](../array#generic_array_methods). It
only expects the `this` value to have a `length` property and
integer-keyed properties. Although strings are also array-like, this
method is not suitable to be applied on them, as strings are immutable.




Examples
--------



### Reversing the elements in an array 


The following example creates an array `items`, containing three
elements, then reverses the array. The call to `reverse()` returns a
reference to the reversed array `items`.



[js]


```js
const items = [1, 2, 3];
console.log(items); // [1, 2, 3]

items.reverse();
console.log(items); // [3, 2, 1]
```





### The reverse() method returns the reference to the same array 


The `reverse()` method returns reference to the original array, so
mutating the returned array will mutate the original array as well.



[js]


```js
const numbers = [3, 2, 4, 1, 5];
const reversed = numbers.reverse();
// numbers and reversed are both in reversed order [5, 1, 4, 2, 3]
reversed[0] = 5;
console.log(numbers[0]); // 5
```


In case you want `reverse()` to not mutate the original array, but
return a
[shallow-copied](https://developer.mozilla.org/en-US/docs/Glossary/Shallow_copy)
array like other array methods (e.g. [`map()`](map)) do, use the
[`toReversed()`](toreversed) method. Alternatively, you can do a shallow
copy before calling `reverse()`, using the [spread
syntax](../../operators/spread_syntax) or [`Array.from()`](from).



[js]


```js
const numbers = [3, 2, 4, 1, 5];
// [...numbers] creates a shallow copy, so reverse() does not mutate the original
const reverted = [...numbers].reverse();
reverted[0] = 5;
console.log(numbers[0]); // 3
```





### Using reverse() on sparse arrays 


Sparse arrays remain sparse after calling `reverse()`. Empty slots are
copied over to their respective new indices as empty slots.



[js]


```js
console.log([1, , 3].reverse()); // [3, empty, 1]
console.log([1, , 3, 4].reverse()); // [4, 3, empty, 1]
```





### Calling reverse() on non-array objects 


The `reverse()` method reads the `length` property of `this`. It then
visits each property having an integer key between `0` and `length / 2`,
and swaps the two corresponding indices on both ends,
[deleting](../../operators/delete) any destination property for which
the source property did not exist.



[js]


```js
const arrayLike = {
  length: 3,
  unrelated: "foo",
  2: 4,
  3: 33, // ignored by reverse() since length is 3
};
console.log(Array.prototype.reverse.call(arrayLike));
// { 0: 4, 3: 33, length: 3, unrelated: 'foo' }
// The index 2 is deleted because there was no index 0 present originally
// The index 3 is unchanged since the length is 3
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.reverse]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.reverse)

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

`reverse`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0


See also 
--------


-   [Polyfill of `Array.prototype.reverse` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array.prototype.join()`](join)
-   [`Array.prototype.sort()`](sort)
-   [`Array.prototype.toReversed()`](toreversed)
-   [`TypedArray.prototype.reverse()`](../typedarray/reverse)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse>

