Array.prototype.with()
======================


The `with()` method of [`Array`](../array) instances is the
[copying](../array#copying_methods_and_mutating_methods) version of
using the [bracket
notation](../../operators/property_accessors#bracket_notation) to change
the value of a given index. It returns a new array with the element at
the given index replaced with the given value.



Syntax
------




[js]


```js
arrayInstance.with(index, value)
```





### Parameters



[`index`](#index)

:   Zero-based index at which to change the array, [converted to an
    integer](../number#integer_conversion).

    -   Negative index counts back from the end of the array --- if
        `index < 0`, `index + array.length` is used.
    -   If the index after normalization is out of bounds, a
        [`RangeError`](../rangeerror) is thrown.

[`value`](#value)

:   Any value to be assigned to the given index.




### Return value 


A new array with the element at `index` replaced with `value`.




### Exceptions



[`RangeError`](../rangeerror)

:   Thrown if `index >= array.length` or `index < -array.length`.




Description
-----------


The `with()` method changes the value of a given index in the array,
returning a new array with the element at the given index replaced with
the given value. The original array is not modified. This allows you to
chain array methods while doing manipulations.

By combining `with()` with [`at()`](at), you can both write and read
(respectively) an array using negative indices.

The `with()` method never produces a [sparse
array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays).
If the source array is sparse, the empty slots will be replaced with
`undefined` in the new array.

The `with()` method is [generic](../array#generic_array_methods). It
only expects the `this` value to have a `length` property and
integer-keyed properties.




Examples
--------



### Creating a new array with a single element changed 




[js]


```js
const arr = [1, 2, 3, 4, 5];
console.log(arr.with(2, 6)); // [1, 2, 6, 4, 5]
console.log(arr); // [1, 2, 3, 4, 5]
```





### Chaining array methods 


With the `with()` method, you can update a single element in an array
and then apply other array methods.



[js]


```js
const arr = [1, 2, 3, 4, 5];
console.log(arr.with(2, 6).map((x) => x ** 2)); // [1, 4, 36, 16, 25]
```





### Using with() on sparse arrays 


The `with()` method always creates a dense array.



[js]


```js
const arr = [1, , 3, 4, , 6];
console.log(arr.with(0, 2)); // [2, undefined, 3, 4, undefined, 6]
```





### Calling with() on non-array objects 


The `with()` method creates and returns a new array. It reads the
`length` property of `this` and then accesses each property whose key is
a nonnegative integer less than `length`. As each property of `this` is
accessed, the array element having an index equal to the key of the
property is set to the value of the property. Finally, the array value
at `index` is set to `value`.



[js]


```js
const arrayLike = {
  length: 3,
  unrelated: "foo",
  0: 5,
  2: 4,
  3: 3, // ignored by with() since length is 3
};
console.log(Array.prototype.with.call(arrayLike, 0, 1));
// [ 1, undefined, 4 ]
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.with]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.with)

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

`with`

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


-   [Polyfill of `Array.prototype.with` in
    `core-js`](https://github.com/zloirock/core-js#change-array-by-copy)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array.prototype.toReversed()`](toreversed)
-   [`Array.prototype.toSorted()`](tosorted)
-   [`Array.prototype.toSpliced()`](tospliced)
-   [`Array.prototype.at()`](at)
-   [`TypedArray.prototype.with()`](../typedarray/with)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/with>

