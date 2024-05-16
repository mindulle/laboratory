Array.prototype.shift()
=======================


The `shift()` method of [`Array`](../array) instances removes the
**first** element from an array and returns that removed element. This
method changes the length of the array.



Try it 
------






Syntax
------




[js]


```js
shift()
```





### Parameters


None.




### Return value 


The removed element from the array; [`undefined`](../undefined) if the
array is empty.




Description
-----------


The `shift()` method removes the element at the zeroth index and shifts
the values at consecutive indexes down, then returns the removed value.
If the [`length`](length) property is 0, [`undefined`](../undefined) is
returned.

The [`pop()`](pop) method has similar behavior to `shift()`, but applied
to the last element in an array.

The `shift()` method is a [mutating
method](../array#copying_methods_and_mutating_methods). It changes the
length and the content of `this`. In case you want the value of `this`
to be the same, but return a new array with the first element removed,
you can use [`arr.slice(1)`](slice) instead.

The `shift()` method is [generic](../array#generic_array_methods). It
only expects the `this` value to have a `length` property and
integer-keyed properties. Although strings are also array-like, this
method is not suitable to be applied on them, as strings are immutable.




Examples
--------



### Removing an element from an array 


The following code displays the `myFish` array before and after removing
its first element. It also displays the removed element:



[js]


```js
const myFish = ["angel", "clown", "mandarin", "surgeon"];

console.log("myFish before:", myFish);
// myFish before: ['angel', 'clown', 'mandarin', 'surgeon']

const shifted = myFish.shift();

console.log("myFish after:", myFish);
// myFish after: ['clown', 'mandarin', 'surgeon']

console.log("Removed this element:", shifted);
// Removed this element: angel
```





### Using shift() method in while loop 


The shift() method is often used in condition inside while loop. In the
following example every iteration will remove the next element from an
array, until it is empty:



[js]


```js
const names = ["Andrew", "Tyrone", "Paul", "Maria", "Gayatri"];

while (typeof (i = names.shift()) !== "undefined") {
  console.log(i);
}
// Andrew, Tyrone, Paul, Maria, Gayatri
```





### Calling shift() on non-array objects 


The `shift()` method reads the `length` property of `this`. If the
[normalized length](../array#normalization_of_the_length_property) is 0,
`length` is set to `0` again (whereas it may be negative or `undefined`
before). Otherwise, the property at `0` is returned, and the rest of the
properties are shifted left by one. The `length` property is decremented
by one.



[js]


```js
const arrayLike = {
  length: 3,
  unrelated: "foo",
  2: 4,
};
console.log(Array.prototype.shift.call(arrayLike));
// undefined, because it is an empty slot
console.log(arrayLike);
// { '1': 4, length: 2, unrelated: 'foo' }

const plainObj = {};
// There's no length property, so the length is 0
Array.prototype.shift.call(plainObj);
console.log(plainObj);
// { length: 0 }
```




Specifications
--------------


  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.shift]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.shift)

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

`shift`

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


-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array.prototype.push()`](push)
-   [`Array.prototype.pop()`](pop)
-   [`Array.prototype.unshift()`](unshift)
-   [`Array.prototype.concat()`](concat)
-   [`Array.prototype.splice()`](splice)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift>

