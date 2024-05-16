Array() constructor
===================


The `Array()` constructor creates [`Array`](../array) objects.



Syntax
------




[js]


```js
new Array()
new Array(element1)
new Array(element1, element2)
new Array(element1, element2, /* …, */ elementN)
new Array(arrayLength)

Array()
Array(element1)
Array(element1, element2)
Array(element1, element2, /* …, */ elementN)
Array(arrayLength)
```


 
**Note:** `Array()` can be called with or without
[`new`](../../operators/new). Both create a new `Array` instance.





### Parameters



[`element1`](#element1), ..., `elementN`

:   A JavaScript array is initialized with the given elements, except in
    the case where a single argument is passed to the `Array`
    constructor and that argument is a number (see the `arrayLength`
    parameter below). Note that this special case only applies to
    JavaScript arrays created with the `Array` constructor, not array
    literals created with the square bracket syntax.

[`arrayLength`](#arraylength)

:   If the only argument passed to the `Array` constructor is an integer
    between 0 and 2^32^ - 1 (inclusive), this returns a new JavaScript
    array with its `length` property set to that number (**Note:** this
    implies an array of `arrayLength` empty slots, not slots with actual
    `undefined` values --- see [sparse
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays)).




### Exceptions



[`RangeError`](../rangeerror)

:   Thrown if there\'s only one argument (`arrayLength`) that is a
    number, but its value is not an integer or not between 0 and 2^32^ -
    1 (inclusive).




Examples
--------



### Array literal notation 


Arrays can be created using the
[literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#array_literals)
notation:



[js]


```js
const fruits = ["Apple", "Banana"];

console.log(fruits.length); // 2
console.log(fruits[0]); // "Apple"
```





### Array constructor with a single parameter 


Arrays can be created using a constructor with a single number
parameter. An array is created with its `length` property set to that
number, and the array elements are empty slots.



[js]


```js
const arrayEmpty = new Array(2);

console.log(arrayEmpty.length); // 2
console.log(arrayEmpty[0]); // undefined; actually, it is an empty slot
console.log(0 in arrayEmpty); // false
console.log(1 in arrayEmpty); // false
```




[js]


```js
const arrayOfOne = new Array("2"); // Not the number 2 but the string "2"

console.log(arrayOfOne.length); // 1
console.log(arrayOfOne[0]); // "2"
```





### Array constructor with multiple parameters 


If more than one argument is passed to the constructor, a new
[`Array`](../array) with the given elements is created.



[js]


```js
const fruits = new Array("Apple", "Banana");

console.log(fruits.length); // 2
console.log(fruits[0]); // "Apple"
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array-constructor]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array-constructor)

  -------------------------------------------------------------------------------------------------------------------


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

`Array`

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




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Array>

