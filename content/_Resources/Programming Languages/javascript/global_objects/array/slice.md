Array.prototype.slice()
=======================


The `slice()` method of [`Array`](../array) instances returns a [shallow
copy](https://developer.mozilla.org/en-US/docs/Glossary/Shallow_copy) of
a portion of an array into a new array object selected from `start` to
`end` (`end` not included) where `start` and `end` represent the index
of items in that array. The original array will not be modified.



Try it 
------






Syntax
------




[js]


```js
slice()
slice(start)
slice(start, end)
```





### Parameters



[`start`](#start) [Optional]

:   Zero-based index at which to start extraction, [converted to an
    integer](../number#integer_conversion).

    -   Negative index counts back from the end of the array --- if
        `start < 0`, `start + array.length` is used.
    -   If `start < -array.length` or `start` is omitted, `0` is used.
    -   If `start >= array.length`, nothing is extracted.

[`end`](#end) [Optional]

:   Zero-based index at which to end extraction, [converted to an
    integer](../number#integer_conversion). `slice()` extracts up to but
    not including `end`.

    -   Negative index counts back from the end of the array --- if
        `end < 0`, `end + array.length` is used.
    -   If `end < -array.length`, `0` is used.
    -   If `end >= array.length` or `end` is omitted, `array.length` is
        used, causing all elements until the end to be extracted.
    -   If `end` is positioned before or at `start` after normalization,
        nothing is extracted.




### Return value 


A new array containing the extracted elements.




Description
-----------


The `slice()` method is a [copying
method](../array#copying_methods_and_mutating_methods). It does not
alter `this` but instead returns a [shallow
copy](https://developer.mozilla.org/en-US/docs/Glossary/Shallow_copy)
that contains some of the same elements as the ones from the original
array.

The `slice()` method preserves empty slots. If the sliced portion is
[sparse](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays),
the returned array is sparse as well.

The `slice()` method is [generic](../array#generic_array_methods). It
only expects the `this` value to have a `length` property and
integer-keyed properties.




Examples
--------



### Return a portion of an existing array 




[js]


```js
const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
const citrus = fruits.slice(1, 3);

// fruits contains ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango']
// citrus contains ['Orange','Lemon']
```





### Using slice 


In the following example, `slice` creates a new array, `newCar`, from
`myCar`. Both include a reference to the object `myHonda`. When the
color of `myHonda` is changed to purple, both arrays reflect the change.



[js]


```js
// Using slice, create newCar from myCar.
const myHonda = {
  color: "red",
  wheels: 4,
  engine: { cylinders: 4, size: 2.2 },
};
const myCar = [myHonda, 2, "cherry condition", "purchased 1997"];
const newCar = myCar.slice(0, 2);

console.log("myCar =", myCar);
console.log("newCar =", newCar);
console.log("myCar[0].color =", myCar[0].color);
console.log("newCar[0].color =", newCar[0].color);

// Change the color of myHonda.
myHonda.color = "purple";
console.log("The new color of my Honda is", myHonda.color);

console.log("myCar[0].color =", myCar[0].color);
console.log("newCar[0].color =", newCar[0].color);
```


This script writes:

```text
myCar = [
  { color: 'red', wheels: 4, engine: { cylinders: 4, size: 2.2 } },
  2,
  'cherry condition',
  'purchased 1997'
]
newCar = [ { color: 'red', wheels: 4, engine: { cylinders: 4, size: 2.2 } }, 2 ]
myCar[0].color = red
newCar[0].color = red
The new color of my Honda is purple
myCar[0].color = purple
newCar[0].color = purple
```




### Calling slice() on non-array objects 


The `slice()` method reads the `length` property of `this`. It then
reads the integer-keyed properties from `start` to `end` and defines
them on a newly created array.



[js]


```js
const arrayLike = {
  length: 3,
  0: 2,
  1: 3,
  2: 4,
  3: 33, // ignored by slice() since length is 3
};
console.log(Array.prototype.slice.call(arrayLike, 1, 3));
// [ 3, 4 ]
```





### Using slice() to convert array-like objects to arrays 


The `slice()` method is often used with [`bind()`](../function/bind) and
[`call()`](../function/call) to create a utility method that converts an
array-like object into an array.



[js]


```js
// slice() is called with `this` passed as the first argument
const slice = Function.prototype.call.bind(Array.prototype.slice);

function list() {
  return slice(arguments);
}

const list1 = list(1, 2, 3); // [1, 2, 3]
```





### Using slice() on sparse arrays 


The array returned from `slice()` may be sparse if the source is sparse.



[js]


```js
console.log([1, 2, , 4, 5].slice(1, 4)); // [2, empty, 4]
```




Specifications
--------------


  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.slice]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.slice)

  ---------------------------------------------------------------------------------------------------------------------------


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

`slice`

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


-   [Polyfill of `Array.prototype.slice` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array.prototype.pop()`](pop)
-   [`Array.prototype.shift()`](shift)
-   [`Array.prototype.concat()`](concat)
-   [`Array.prototype.splice()`](splice)
-   [`TypedArray.prototype.slice()`](../typedarray/slice)
-   [`String.prototype.slice()`](../string/slice)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice>

