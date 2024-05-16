Array.prototype.findLastIndex()
===============================


The `findLastIndex()` method of [`Array`](../array) instances iterates
the array in reverse order and returns the index of the first element
that satisfies the provided testing function. If no elements satisfy the
testing function, -1 is returned.

See also the [`findLast()`](findlast) method, which returns the value of
last element that satisfies the testing function (rather than its
index).



Try it 
------






Syntax
------




[js]


```js
findLastIndex(callbackFn)
findLastIndex(callbackFn, thisArg)
```





### Parameters



[`callbackFn`](#callbackfn)

:   A function to execute for each element in the array. It should
    return a
    [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
    value to indicate a matching element has been found, and a
    [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
    value otherwise. The function is called with the following
    arguments:

    [`element`](#element)

    :   The current element being processed in the array.

    [`index`](#index)

    :   The index of the current element being processed in the array.

    [`array`](#array)

    :   The array `findLastIndex()` was called upon.

[`thisArg`](#thisarg) [Optional]

:   A value to use as `this` when executing `callbackFn`. See [iterative
    methods](../array#iterative_methods).




### Return value 


The index of the last (highest-index) element in the array that passes
the test. Otherwise `-1` if no matching element is found.




Description
-----------


The `findLastIndex()` method is an [iterative
method](../array#iterative_methods). It calls a provided `callbackFn`
function once for each element in an array in descending-index order,
until `callbackFn` returns a
[truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
value. `findLastIndex()` then returns the index of that element and
stops iterating through the array. If `callbackFn` never returns a
truthy value, `findLastIndex()` returns `-1`. Read the [iterative
methods](../array#iterative_methods) section for more information about
how these methods work in general.

`callbackFn` is invoked for *every* index of the array, not just those
with assigned values. Empty slots in [sparse
arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays)
behave the same as `undefined`.

The `findLastIndex()` method is
[generic](../array#generic_array_methods). It only expects the `this`
value to have a `length` property and integer-keyed properties.




Examples
--------



### Find the index of the last prime number in an array 


The following example returns the index of the last element in the array
that is a prime number, or `-1` if there is no prime number.



[js]


```js
function isPrime(element) {
  if (element % 2 === 0 || element < 2) {
    return false;
  }
  for (let factor = 3; factor <= Math.sqrt(element); factor += 2) {
    if (element % factor === 0) {
      return false;
    }
  }
  return true;
}

console.log([4, 6, 8, 12].findLastIndex(isPrime)); // -1, not found
console.log([4, 5, 7, 8, 9, 11, 12].findLastIndex(isPrime)); // 5
```





### Using the third argument of callbackFn 


The `array` argument is useful if you want to access another element in
the array, especially when you don\'t have an existing variable that
refers to the array. The following example first uses `filter()` to
extract the positive values and then uses `findLastIndex()` to find the
last element that is less than its neighbors.



[js]


```js
const numbers = [3, -1, 1, 4, 1, 5, 9, 2, 6];
const lastTrough = numbers
  .filter((num) => num > 0)
  .findLastIndex((num, idx, arr) => {
    // Without the arr argument, there's no way to easily access the
    // intermediate array without saving it to a variable.
    if (idx > 0 && num >= arr[idx - 1]) return false;
    if (idx < arr.length - 1 && num >= arr[idx + 1]) return false;
    return true;
  });
console.log(lastTrough); // 6
```





### Using findLastIndex() on sparse arrays 


You can search for `undefined` in a sparse array and get the index of an
empty slot.



[js]


```js
console.log([1, , 3].findLastIndex((x) => x === undefined)); // 1
```





### Calling findLastIndex() on non-array objects 


The `findLastIndex()` method reads the `length` property of `this` and
then accesses each property whose key is a nonnegative integer less than
`length`.



[js]


```js
const arrayLike = {
  length: 3,
  0: 2,
  1: 7.3,
  2: 4,
  3: 3, // ignored by findLastIndex() since length is 3
};
console.log(
  Array.prototype.findLastIndex.call(arrayLike, (x) => Number.isInteger(x)),
); // 2
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.findlastindex]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.findlastindex)

  -------------------------------------------------------------------------------------------------------------------------------------------


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

`findLastIndex`

97

97

104

83

15.4

97

104

68

15.4

18.0

97

1.16

18.0.0


See also 
--------


-   [Polyfill of `Array.prototype.findLastIndex` in
    `core-js`](https://github.com/zloirock/core-js#array-find-from-last)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array.prototype.find()`](find)
-   [`Array.prototype.findIndex()`](findindex)
-   [`Array.prototype.findLast()`](findlast)
-   [`Array.prototype.indexOf()`](indexof)
-   [`Array.prototype.lastIndexOf()`](lastindexof)
-   [`TypedArray.prototype.findLastIndex()`](../typedarray/findlastindex)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findLastIndex>

