Array.prototype\[@\@iterator\]()
================================


The `[@@iterator]()` method of [`Array`](../array) instances implements
the [iterable protocol](../../iteration_protocols) and allows arrays to
be consumed by most syntaxes expecting iterables, such as the [spread
syntax](../../operators/spread_syntax) and
[`for...of`](../../statements/for...of) loops. It returns an [array
iterator object](../iterator) that yields the value of each index in the
array.

The initial value of this property is the same function object as the
initial value of the [`Array.prototype.values`](values) property.



Try it 
------






Syntax
------




[js]


```js
array[Symbol.iterator]()
```





### Parameters


None.




### Return value 


The same return value as [`Array.prototype.values()`](values): a new
[iterable iterator object](../iterator) that yields the value of each
index in the array.




Examples
--------



### Iteration using for\...of loop 


Note that you seldom need to call this method directly. The existence of
the `@@iterator` method makes arrays
[iterable](../../iteration_protocols#the_iterable_protocol), and
iterating syntaxes like the `for...of` loop automatically call this
method to obtain the iterator to loop over.

#### HTML



[html]


```html
<ul id="letterResult"></ul>
```


#### JavaScript



[js]


```js
const arr = ["a", "b", "c"];
const letterResult = document.getElementById("letterResult");
for (const letter of arr) {
  const li = document.createElement("li");
  li.textContent = letter;
  letterResult.appendChild(li);
}
```


#### Result

 





### Manually hand-rolling the iterator 


You may still manually call the `next()` method of the returned iterator
object to achieve maximum control over the iteration process.



[js]


```js
const arr = ["a", "b", "c", "d", "e"];
const arrIter = arr[Symbol.iterator]();
console.log(arrIter.next().value); // a
console.log(arrIter.next().value); // b
console.log(arrIter.next().value); // c
console.log(arrIter.next().value); // d
console.log(arrIter.next().value); // e
```





### Handling strings and string arrays with the same function 


Because both [strings](../string/@@iterator) and arrays implement the
iterable protocol, a generic function can be designed to handle both
inputs in the same fashion. This is better than calling
[`Array.prototype.values()`](values) directly, which requires the input
to be an array, or at least an object with such a method.



[js]


```js
function logIterable(it) {
  if (typeof it[Symbol.iterator] !== "function") {
    console.log(it, "is not iterable.");
    return;
  }
  for (const letter of it) {
    console.log(letter);
  }
}

// Array
logIterable(["a", "b", "c"]);
// a
// b
// c

// String
logIterable("abc");
// a
// b
// c

// Number
logIterable(123);
// 123 is not iterable.
```




Specifications
--------------


  --------------------------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype-@\@iterator]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype-@@iterator)

  --------------------------------------------------------------------------------------------------------------------------------------


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

`@@iterator`

38

12

36

27--36A placeholder property named `@@iterator` is used.

17--27A placeholder property named `iterator` is used.

25

10

38

36

27--36A placeholder property named `@@iterator` is used.

17--27A placeholder property named `iterator` is used.

25

10

3.0

38

1.0

0.12.0


See also 
--------


-   [Polyfill of `Array.prototype[@@iterator]` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array.prototype.keys()`](keys)
-   [`Array.prototype.entries()`](entries)
-   [`Array.prototype.values()`](values)
-   [`TypedArray.prototype[@@iterator]()`](../typedarray/@@iterator)
-   [`String.prototype[@@iterator]()`](../string/@@iterator)
-   [`Symbol.iterator`](../symbol/iterator)
-   [Iteration protocols](../../iteration_protocols)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/@@iterator>

