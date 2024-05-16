Array.prototype.unshift()
=========================


The `unshift()` method of [`Array`](../array) instances adds the
specified elements to the beginning of an array and returns the new
length of the array.



Try it 
------






Syntax
------




[js]


```js
unshift()
unshift(element1)
unshift(element1, element2)
unshift(element1, element2, /* …, */ elementN)
```





### Parameters



[`element1`](#element1), ..., `elementN`

:   The elements to add to the front of the `arr`.




### Return value 


The new [`length`](length) property of the object upon which the method
was called.




Description
-----------


The `unshift()` method inserts the given values to the beginning of an
array-like object.

[`Array.prototype.push()`](push) has similar behavior to `unshift()`,
but applied to the end of an array.

Please note that, if multiple elements are passed as parameters,
they\'re inserted in chunk at the beginning of the object, in the exact
same order they were passed as parameters. Hence, calling `unshift()`
with `n` arguments **once**, or calling it `n` times with **1** argument
(with a loop, for example), don\'t yield the same results.

See example:



[js]


```js
let arr = [4, 5, 6];

arr.unshift(1, 2, 3);
console.log(arr);
// [1, 2, 3, 4, 5, 6]

arr = [4, 5, 6]; // resetting the array

arr.unshift(1);
arr.unshift(2);
arr.unshift(3);

console.log(arr);
// [3, 2, 1, 4, 5, 6]
```


The `unshift()` method is [generic](../array#generic_array_methods). It
only expects the `this` value to have a `length` property and
integer-keyed properties. Although strings are also array-like, this
method is not suitable to be applied on them, as strings are immutable.




Examples
--------



### Using unshift() 




[js]


```js
const arr = [1, 2];

arr.unshift(0); // result of the call is 3, which is the new array length
// arr is [0, 1, 2]

arr.unshift(-2, -1); // the new array length is 5
// arr is [-2, -1, 0, 1, 2]

arr.unshift([-4, -3]); // the new array length is 6
// arr is [[-4, -3], -2, -1, 0, 1, 2]

arr.unshift([-7, -6], [-5]); // the new array length is 8
// arr is [ [-7, -6], [-5], [-4, -3], -2, -1, 0, 1, 2 ]
```





### Calling unshift() on non-array objects 


The `unshift()` method reads the `length` property of `this`. It shifts
all indices in the range `0` to `length - 1` right by the number of
arguments (incrementing their values by this number). Then, it sets each
index starting at `0` with the arguments passed to `unshift()`. Finally,
it sets the `length` to the previous length plus the number of prepended
elements.



[js]


```js
const arrayLike = {
  length: 3,
  unrelated: "foo",
  2: 4,
};
Array.prototype.unshift.call(arrayLike, 1, 2);
console.log(arrayLike);
// { '0': 1, '1': 2, '4': 4, length: 5, unrelated: 'foo' }

const plainObj = {};
// There's no length property, so the length is 0
Array.prototype.unshift.call(plainObj, 1, 2);
console.log(plainObj);
// { '0': 1, '1': 2, length: 2 }
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.unshift]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.unshift)

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

`unshift`

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


-   [Polyfill of `Array.prototype.unshift` in `core-js` with fixes of
    this method](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array.prototype.push()`](push)
-   [`Array.prototype.pop()`](pop)
-   [`Array.prototype.shift()`](shift)
-   [`Array.prototype.concat()`](concat)
-   [`Array.prototype.splice()`](splice)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift>

