Array.prototype.flatMap()
=========================

Baseline [Widely available]
--------------------------------------


This feature is well established and works across many devices and
browser versions. It's been available across browsers since January
2020.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FArray%2FflatMap&level=high)



The `flatMap()` method of [`Array`](../array) instances returns a new
array formed by applying a given callback function to each element of
the array, and then flattening the result by one level. It is identical
to a [`map()`](map) followed by a [`flat()`](flat) of depth 1
(`arr.map(...args).flat()`), but slightly more efficient than calling
those two methods separately.



Try it 
------






Syntax
------




[js]


```js
flatMap(callbackFn)
flatMap(callbackFn, thisArg)
```





### Parameters



[`callbackFn`](#callbackfn)

:   A function to execute for each element in the array. It should
    return an array containing new elements of the new array, or a
    single non-array value to be added to the new array. The function is
    called with the following arguments:

    [`element`](#element)

    :   The current element being processed in the array.

    [`index`](#index)

    :   The index of the current element being processed in the array.

    [`array`](#array)

    :   The array `flatMap()` was called upon.

[`thisArg`](#thisarg) [Optional]

:   A value to use as `this` when executing `callbackFn`. See [iterative
    methods](../array#iterative_methods).




### Return value 


A new array with each element being the result of the callback function
and flattened by a depth of 1.




Description
-----------


The `flatMap()` method is an [iterative
method](../array#iterative_methods). See [`Array.prototype.map()`](map)
for a detailed description of the callback function. The `flatMap()`
method is identical to [`map(callbackFn, thisArg)`](map) followed by
[`flat(1)`](flat) --- for each element, it produces an array of new
elements, and concatenates the resulting arrays together to form a new
array. Read the [iterative methods](../array#iterative_methods) section
for more information about how these methods work in general.

The `flatMap()` method is [generic](../array#generic_array_methods). It
only expects the `this` value to have a `length` property and
integer-keyed properties. However, the value returned from `callbackFn`
must be an array if it is to be flattened.




### Alternative


#### Pre-allocate and explicitly iterate 



[js]


```js
const arr = [1, 2, 3, 4];

arr.flatMap((x) => [x, x * 2]);
// is equivalent to
const n = arr.length;
const acc = new Array(n * 2);
for (let i = 0; i < n; i++) {
  const x = arr[i];
  acc[i * 2] = x;
  acc[i * 2 + 1] = x * 2;
}
// [1, 2, 2, 4, 3, 6, 4, 8]
```


Note that in this particular case the `flatMap` approach is slower than
the for-loop approach --- due to the creation of temporary arrays that
must be garbage collected, as well as the return array not needing to be
frequently resized. However, `flatMap` may still be the correct solution
in cases where its flexibility and readability are desired.




Examples
--------



### map() and flatMap() 




[js]


```js
const arr1 = [1, 2, 3, 4];

arr1.map((x) => [x * 2]);
// [[2], [4], [6], [8]]

arr1.flatMap((x) => [x * 2]);
// [2, 4, 6, 8]

// only one level is flattened
arr1.flatMap((x) => [[x * 2]]);
// [[2], [4], [6], [8]]
```


While the above could have been achieved by using map itself, here is an
example that better showcases the use of `flatMap()`.

Let\'s generate a list of words from a list of sentences.



[js]


```js
const arr1 = ["it's Sunny in", "", "California"];

arr1.map((x) => x.split(" "));
// [["it's","Sunny","in"],[""],["California"]]

arr1.flatMap((x) => x.split(" "));
// ["it's","Sunny","in", "", "California"]
```


Notice, the output list length can be different from the input list
length.




### For adding and removing items during a map() 


`flatMap` can be used as a way to add and remove items (modify the
number of items) during a `map`. In other words, it allows you to map
*many items to many items* (by handling each input item separately),
rather than always *one-to-one*. In this sense, it works like the
opposite of [filter](filter). Return a 1-element array to keep the item,
a multiple-element array to add items, or a 0-element array to remove
the item.



[js]


```js
// Let's say we want to remove all the negative numbers
// and split the odd numbers into an even number and a 1
const a = [5, 4, -3, 20, 17, -33, -4, 18];
//         |\  \  x   |  | \   x   x   |
//        [4,1, 4,   20, 16, 1,       18]

const result = a.flatMap((n) => {
  if (n < 0) {
    return [];
  }
  return n % 2 === 0 ? [n] : [n - 1, 1];
});
console.log(result); // [4, 1, 4, 20, 16, 1, 18]
```





### Using the third argument of callbackFn 


The `array` argument is useful if you want to access another element in
the array, especially when you don\'t have an existing variable that
refers to the array. The following example first uses `filter()` to
extract operational stations and then uses `flatMap()` to create a new
array where each element contains a station and its next station. On the
last station, it returns an empty array to exclude it from the final
array.



[js]


```js
const stations = ["New Haven", "West Haven", "Milford (closed)", "Stratford"];
const line = stations
  .filter((name) => !name.endsWith("(closed)"))
  .flatMap((name, idx, arr) => {
    // Without the arr argument, there's no way to easily access the
    // intermediate array without saving it to a variable.
    if (idx === arr.length - 1) return []; // last station has no next station
    return [`${name} - ${arr[idx + 1]}`];
  });
console.log(line); // ['New Haven - West Haven', 'West Haven - Stratford']
```


The `array` argument is *not* the array that is being built --- there is
no way to access the array being built from the callback function.




### Using flatMap() on sparse arrays 


The `callbackFn` won\'t be called for empty slots in the source array
because `map()` doesn\'t, while `flat()` ignores empty slots in the
returned arrays.



[js]


```js
console.log([1, 2, , 4, 5].flatMap((x) => [x, x * 2])); // [1, 2, 2, 4, 4, 8, 5, 10]
console.log([1, 2, 3, 4].flatMap((x) => [, x * 2])); // [2, 4, 6, 8]
```





### Calling flatMap() on non-array objects 


The `flatMap()` method reads the `length` property of `this` and then
accesses each property whose key is a nonnegative integer less than
`length`. If the return value of the callback function is not an array,
it is always directly appended to the result array.



[js]


```js
const arrayLike = {
  length: 3,
  0: 1,
  1: 2,
  2: 3,
  3: 4, // ignored by flatMap() since length is 3
};
console.log(Array.prototype.flatMap.call(arrayLike, (x) => [x, x * 2]));
// [1, 2, 2, 4, 3, 6]

// Array-like objects returned from the callback won't be flattened
console.log(
  Array.prototype.flatMap.call(arrayLike, (x) => ({
    length: 1,
    0: x,
  })),
);
// [ { '0': 1, length: 1 }, { '0': 2, length: 1 }, { '0': 3, length: 1 } ]
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.flatmap]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.flatmap)

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

`flatMap`

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


-   [Polyfill of `Array.prototype.flatMap` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array.prototype.concat()`](concat)
-   [`Array.prototype.flat()`](flat)
-   [`Array.prototype.map()`](map)
-   [`Array.prototype.reduce()`](reduce)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/flatMap>

