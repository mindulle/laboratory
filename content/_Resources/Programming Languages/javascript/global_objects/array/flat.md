Array.prototype.flat()
======================

Baseline [Widely available]
--------------------------------------


This feature is well established and works across many devices and
browser versions. It's been available across browsers since January
2020.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FArray%2Fflat&level=high)



The `flat()` method of [`Array`](../array) instances creates a new array
with all sub-array elements concatenated into it recursively up to the
specified depth.



Try it 
------






Syntax
------




[js]


```js
flat()
flat(depth)
```





### Parameters



[`depth`](#depth) [Optional]

:   The depth level specifying how deep a nested array structure should
    be flattened. Defaults to 1.




### Return value 


A new array with the sub-array elements concatenated into it.




Description
-----------


The `flat()` method is a [copying
method](../array#copying_methods_and_mutating_methods). It does not
alter `this` but instead returns a [shallow
copy](https://developer.mozilla.org/en-US/docs/Glossary/Shallow_copy)
that contains the same elements as the ones from the original array.

The `flat()` method ignores empty slots if the array being flattened is
[sparse](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays).
For example, if `depth` is 1, both empty slots in the root array and in
the first level of nested arrays are ignored, but empty slots in further
nested arrays are preserved with the arrays themselves.

The `flat()` method is [generic](../array#generic_array_methods). It
only expects the `this` value to have a `length` property and
integer-keyed properties. However, its elements must be arrays if they
are to be flattened.




Examples
--------



### Flattening nested arrays 




[js]


```js
const arr1 = [1, 2, [3, 4]];
arr1.flat();
// [1, 2, 3, 4]

const arr2 = [1, 2, [3, 4, [5, 6]]];
arr2.flat();
// [1, 2, 3, 4, [5, 6]]

const arr3 = [1, 2, [3, 4, [5, 6]]];
arr3.flat(2);
// [1, 2, 3, 4, 5, 6]

const arr4 = [1, 2, [3, 4, [5, 6, [7, 8, [9, 10]]]]];
arr4.flat(Infinity);
// [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```





### Using flat() on sparse arrays 


The `flat()` method removes empty slots in arrays:



[js]


```js
const arr5 = [1, 2, , 4, 5];
console.log(arr5.flat()); // [1, 2, 4, 5]

const array = [1, , 3, ["a", , "c"]];
console.log(array.flat()); // [ 1, 3, "a", "c" ]

const array2 = [1, , 3, ["a", , ["d", , "e"]]];
console.log(array2.flat()); // [ 1, 3, "a", ["d", empty, "e"] ]
console.log(array2.flat(2)); // [ 1, 3, "a", "d", "e"]
```





### Calling flat() on non-array objects 


The `flat()` method reads the `length` property of `this` and then
accesses each property whose key is a nonnegative integer less than
`length`. If the element is not an array, it\'s directly appended to the
result. If the element is an array, it\'s flattened according to the
`depth` parameter.



[js]


```js
const arrayLike = {
  length: 3,
  0: [1, 2],
  // Array-like objects aren't flattened
  1: { length: 2, 0: 3, 1: 4 },
  2: 5,
  3: 3, // ignored by flat() since length is 3
};
console.log(Array.prototype.flat.call(arrayLike));
// [ 1, 2, { '0': 3, '1': 4, length: 2 }, 5 ]
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.flat]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.flat)

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

`flat`

69

79

62

56

12

69

62

48

12

10.0

69

1.0

11.0.0


See also 
--------


-   [Polyfill of `Array.prototype.flat` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array.prototype.concat()`](concat)
-   [`Array.prototype.flatMap()`](flatmap)
-   [`Array.prototype.map()`](map)
-   [`Array.prototype.reduce()`](reduce)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/flat>

