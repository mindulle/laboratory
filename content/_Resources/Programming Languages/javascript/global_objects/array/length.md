Array: length
=============


The `length` data property of an [`Array`](../array) instance represents
the number of elements in that array. The value is an unsigned, 32-bit
integer that is always numerically greater than the highest index in the
array.



Try it 
------






Value
-----


A nonnegative integer less than 2^32^.


Property attributes of `Array: length`




Writable

yes

Enumerable

no

Configurable

no


Description
-----------


The value of the `length` property is a nonnegative integer with a value
less than 2^32^.



[js]


```js
const listA = [1, 2, 3];
const listB = new Array(6);

console.log(listA.length);
// 3

console.log(listB.length);
// 6

listB.length = 2 ** 32; // 4294967296
// RangeError: Invalid array length

const listC = new Array(-100); // Negative numbers are not allowed
// RangeError: Invalid array length
```


The array object observes the `length` property, and automatically syncs
the `length` value with the array\'s content. This means:

-   Setting `length` to a value smaller than the current length
    truncates the array --- elements beyond the new `length` are
    deleted.
-   Setting any array index (a nonnegative integer smaller than 2^32^)
    beyond the current `length` extends the array --- the `length`
    property is increased to reflect the new highest index.
-   Setting `length` to an invalid value (e.g. a negative number or a
    non-integer) throws a `RangeError` exception.

When `length` is set to a bigger value than the current length, the
array is extended by adding [empty
slots](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays),
not actual `undefined` values. Empty slots have some special
interactions with array methods; see [array methods and empty
slots](../array#array_methods_and_empty_slots).



[js]


```js
const arr = [1, 2];
console.log(arr);
// [ 1, 2 ]

arr.length = 5; // set array length to 5 while currently 2.
console.log(arr);
// [ 1, 2, <3 empty items> ]

arr.forEach((element) => console.log(element));
// 1
// 2
```


See also [Relationship between `length` and numerical
properties](../array#relationship_between_length_and_numerical_properties).




Examples
--------



### Iterating over an array 


In the following example, the array `numbers` is iterated through by
looking at the `length` property. The value in each element is then
doubled.



[js]


```js
const numbers = [1, 2, 3, 4, 5];
const length = numbers.length;
for (let i = 0; i < length; i++) {
  numbers[i] *= 2;
}
// numbers is now [2, 4, 6, 8, 10]
```





### Shortening an array 


The following example shortens the array `numbers` to a length of 3 if
the current length is greater than 3.



[js]


```js
const numbers = [1, 2, 3, 4, 5];

if (numbers.length > 3) {
  numbers.length = 3;
}

console.log(numbers); // [1, 2, 3]
console.log(numbers.length); // 3
console.log(numbers[3]); // undefined; the extra elements are deleted
```





### Create empty array of fixed length 


Setting `length` to a value greater than the current length creates a
[sparse
array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays).



[js]


```js
const numbers = [];
numbers.length = 3;
console.log(numbers); // [empty x 3]
```





### Array with non-writable length 


The `length` property is automatically updated by the array when
elements are added beyond the current length. If the `length` property
is made non-writable, the array will not be able to update it. This
causes an error in [strict mode](../../strict_mode).



[js]


```js
"use strict";

const numbers = [1, 2, 3, 4, 5];
Object.defineProperty(numbers, "length", { writable: false });
numbers[5] = 6; // TypeError: Cannot assign to read only property 'length' of object '[object Array]'
numbers.push(5); // // TypeError: Cannot assign to read only property 'length' of object '[object Array]'
```




Specifications
--------------


  ---------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-properties-of-array-instances-length]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-properties-of-array-instances-length)

  ---------------------------------------------------------------------------------------------------------------------------------------------------------


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

`length`

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

≤37

1.0

0.10.0


See also 
--------


-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`TypedArray.prototype.length`](../typedarray/length)
-   [`String`: `length`](../string/length)
-   [RangeError: invalid array
    length](../../errors/invalid_array_length)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/length>

