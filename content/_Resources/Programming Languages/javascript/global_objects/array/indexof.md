Array.prototype.indexOf()
=========================


The `indexOf()` method of [`Array`](../array) instances returns the
first index at which a given element can be found in the array, or -1 if
it is not present.



Try it 
------






Syntax
------




[js]


```js
indexOf(searchElement)
indexOf(searchElement, fromIndex)
```





### Parameters



[`searchElement`](#searchelement)

:   Element to locate in the array.

[`fromIndex`](#fromindex) [Optional]

:   Zero-based index at which to start searching, [converted to an
    integer](../number#integer_conversion).

    -   Negative index counts back from the end of the array --- if
        `fromIndex < 0`, `fromIndex + array.length` is used. Note, the
        array is still searched from front to back in this case.
    -   If `fromIndex < -array.length` or `fromIndex` is omitted, `0` is
        used, causing the entire array to be searched.
    -   If `fromIndex >= array.length`, the array is not searched and
        `-1` is returned.




### Return value 


The first index of `searchElement` in the array; `-1` if not found.




Description
-----------


The `indexOf()` method compares `searchElement` to elements of the array
using [strict equality](../../operators/strict_equality) (the same
algorithm used by the `===` operator). [`NaN`](../nan) values are never
compared as equal, so `indexOf()` always returns `-1` when
`searchElement` is `NaN`.

The `indexOf()` method skips empty slots in [sparse
arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays).

The `indexOf()` method is [generic](../array#generic_array_methods). It
only expects the `this` value to have a `length` property and
integer-keyed properties.




Examples
--------



### Using indexOf() 


The following example uses `indexOf()` to locate values in an array.



[js]


```js
const array = [2, 9, 9];
array.indexOf(2); // 0
array.indexOf(7); // -1
array.indexOf(9, 2); // 2
array.indexOf(2, -1); // -1
array.indexOf(2, -3); // 0
```


You cannot use `indexOf()` to search for `NaN`.



[js]


```js
const array = [NaN];
array.indexOf(NaN); // -1
```





### Finding all the occurrences of an element 




[js]


```js
const indices = [];
const array = ["a", "b", "a", "c", "a", "d"];
const element = "a";
let idx = array.indexOf(element);
while (idx !== -1) {
  indices.push(idx);
  idx = array.indexOf(element, idx + 1);
}
console.log(indices);
// [0, 2, 4]
```





### Finding if an element exists in the array or not and updating the array 




[js]


```js
function updateVegetablesCollection(veggies, veggie) {
  if (veggies.indexOf(veggie) === -1) {
    veggies.push(veggie);
    console.log(`New veggies collection is: ${veggies}`);
  } else {
    console.log(`${veggie} already exists in the veggies collection.`);
  }
}

const veggies = ["potato", "tomato", "chillies", "green-pepper"];

updateVegetablesCollection(veggies, "spinach");
// New veggies collection is: potato,tomato,chillies,green-pepper,spinach
updateVegetablesCollection(veggies, "spinach");
// spinach already exists in the veggies collection.
```





### Using indexOf() on sparse arrays 


You cannot use `indexOf()` to search for empty slots in sparse arrays.



[js]


```js
console.log([1, , 3].indexOf(undefined)); // -1
```





### Calling indexOf() on non-array objects 


The `indexOf()` method reads the `length` property of `this` and then
accesses each property whose key is a nonnegative integer less than
`length`.



[js]


```js
const arrayLike = {
  length: 3,
  0: 2,
  1: 3,
  2: 4,
  3: 5, // ignored by indexOf() since length is 3
};
console.log(Array.prototype.indexOf.call(arrayLike, 2));
// 0
console.log(Array.prototype.indexOf.call(arrayLike, 5));
// -1
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.indexof]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.indexof)

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

`indexOf`

1

12

1.5

9.5

3

18

4

10.1

1

1.0

≤37

1.0

0.10.0


See also 
--------


-   [Polyfill of `Array.prototype.indexOf` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array.prototype.findIndex()`](findindex)
-   [`Array.prototype.findLastIndex()`](findlastindex)
-   [`Array.prototype.lastIndexOf()`](lastindexof)
-   [`TypedArray.prototype.indexOf()`](../typedarray/indexof)
-   [`String.prototype.indexOf()`](../string/indexof)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf>

