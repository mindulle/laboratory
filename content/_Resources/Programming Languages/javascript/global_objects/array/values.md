Array.prototype.values()
========================


The `values()` method of [`Array`](../array) instances returns a new
*[array iterator](../iterator)* object that iterates the value of each
item in the array.



Try it 
------






Syntax
------




[js]


```js
values()
```





### Parameters


None.




### Return value 


A new [iterable iterator object](../iterator).




Description
-----------


`Array.prototype.values()` is the default implementation of
[`Array.prototype[@@iterator]()`](@@iterator).



[js]


```js
Array.prototype.values === Array.prototype[Symbol.iterator]; // true
```


When used on [sparse
arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays),
the `values()` method iterates empty slots as if they have the value
`undefined`.

The `values()` method is [generic](../array#generic_array_methods). It
only expects the `this` value to have a `length` property and
integer-keyed properties.




Examples
--------



### Iteration using for\...of loop 


Because `values()` returns an iterable iterator, you can use a
[`for...of`](../../statements/for...of) loop to iterate it.



[js]


```js
const arr = ["a", "b", "c", "d", "e"];
const iterator = arr.values();

for (const letter of iterator) {
  console.log(letter);
} // "a" "b" "c" "d" "e"
```





### Iteration using next() 


Because the return value is also an iterator, you can directly call its
`next()` method.



[js]


```js
const arr = ["a", "b", "c", "d", "e"];
const iterator = arr.values();
iterator.next(); // { value: "a", done: false }
iterator.next(); // { value: "b", done: false }
iterator.next(); // { value: "c", done: false }
iterator.next(); // { value: "d", done: false }
iterator.next(); // { value: "e", done: false }
iterator.next(); // { value: undefined, done: true }
console.log(iterator.next().value); // undefined
```





### Reusing the iterable 


 
**Warning:** The array iterator object should be a one-time use object.
Do not reuse it.


The iterable returned from `values()` is not reusable. When
`next().done = true` or `currentIndex > length`, [the `for...of` loop
ends](../../iteration_protocols#interactions_between_the_language_and_iteration_protocols),
and further iterating it has no effect.



[js]


```js
const arr = ["a", "b", "c", "d", "e"];
const values = arr.values();
for (const letter of values) {
  console.log(letter);
}
// "a" "b" "c" "d" "e"
for (const letter of values) {
  console.log(letter);
}
// undefined
```


If you use a [`break`](../../statements/break) statement to end the
iteration early, the iterator can resume from the current position when
continuing to iterate it.



[js]


```js
const arr = ["a", "b", "c", "d", "e"];
const values = arr.values();
for (const letter of values) {
  console.log(letter);
  if (letter === "b") {
    break;
  }
}
// "a" "b"

for (const letter of values) {
  console.log(letter);
}
// "c" "d" "e"
```





### Mutations during iteration 


There are no values stored in the array iterator object returned from
`values()`; instead, it stores the address of the array used in its
creation, and reads the currently visited index on each iteration.
Therefore, its iteration output depends on the value stored in that
index at the time of stepping. If the values in the array changed, the
array iterator object\'s values change too.



[js]


```js
const arr = ["a", "b", "c", "d", "e"];
const iterator = arr.values();
console.log(iterator); // Array Iterator { }
console.log(iterator.next().value); // "a"
arr[1] = "n";
console.log(iterator.next().value); // "n"
```





### Iterating sparse arrays 


`values()` will visit empty slots as if they are `undefined`.



[js]


```js
for (const element of [, "a"].values()) {
  console.log(element);
}
// undefined
// 'a'
```





### Calling values() on non-array objects 


The `values()` method reads the `length` property of `this` and then
accesses each property whose key is a nonnegative integer less than
`length`.



[js]


```js
const arrayLike = {
  length: 3,
  0: "a",
  1: "b",
  2: "c",
  3: "d", // ignored by values() since length is 3
};
for (const entry of Array.prototype.values.call(arrayLike)) {
  console.log(entry);
}
// a
// b
// c
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.values]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.values)

  -----------------------------------------------------------------------------------------------------------------------------


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

`values`

66

14

60

53

9

66

60

47

9

9.0

66

1.0

10.9.00.12.0--4.0.0


See also 
--------


-   [Polyfill of `Array.prototype.values` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array.prototype.entries()`](entries)
-   [`Array.prototype.keys()`](keys)
-   [`Array.prototype[@@iterator]()`](@@iterator)
-   [`TypedArray.prototype.values()`](../typedarray/values)
-   [Iteration protocols](../../iteration_protocols)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/values>

