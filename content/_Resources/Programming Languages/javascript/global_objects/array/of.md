Array.of()
==========


The `Array.of()` static method creates a new `Array` instance from a
variable number of arguments, regardless of number or type of the
arguments.



Try it 
------






Syntax
------




[js]


```js
Array.of()
Array.of(element1)
Array.of(element1, element2)
Array.of(element1, element2, /* …, */ elementN)
```





### Parameters



[`element1`](#element1), ..., `elementN`

:   Elements used to create the array.




### Return value 


A new [`Array`](../array) instance.




Description
-----------


The difference between `Array.of()` and the [`Array()`](array)
constructor is in the handling of single arguments: `Array.of(7)`
creates an array with a single element, `7`, whereas `Array(7)` creates
an empty array with a `length` property of `7`. (That implies an array
of 7 empty slots, not slots with actual [`undefined`](../undefined)
values.)



[js]


```js
Array.of(7); // [7]
Array(7); // array of 7 empty slots

Array.of(1, 2, 3); // [1, 2, 3]
Array(1, 2, 3); // [1, 2, 3]
```


The `Array.of()` method is a generic factory method. For example, if a
subclass of `Array` inherits the `of()` method, the inherited `of()`
method will return new instances of the subclass instead of `Array`
instances. In fact, the `this` value can be any constructor function
that accepts a single argument representing the length of the new array,
and the constructor will be called with the number of arguments passed
to `of()`. The final `length` will be set again when all elements are
assigned. If the `this` value is not a constructor function, the plain
`Array` constructor is used instead.




Examples
--------



### Using Array.of() 




[js]


```js
Array.of(1); // [1]
Array.of(1, 2, 3); // [1, 2, 3]
Array.of(undefined); // [undefined]
```





### Calling of() on non-array constructors 


The `of()` method can be called on any constructor function that accepts
a single argument representing the length of the new array.



[js]


```js
function NotArray(len) {
  console.log("NotArray called with length", len);
}

console.log(Array.of.call(NotArray, 1, 2, 3));
// NotArray called with length 3
// NotArray { '0': 1, '1': 2, '2': 3, length: 3 }

console.log(Array.of.call(Object)); // [Number: 0] { length: 0 }
```


When the `this` value is not a constructor, a plain `Array` object is
returned.



[js]


```js
console.log(Array.of.call({}, 1)); // [ 1 ]
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.of]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.of)

  -------------------------------------------------------------------------------------------------


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

`of`

45

12

25

26

9

39

25

26

9

4.0

39

1.0

4.0.0


See also 
--------


-   [Polyfill of `Array.of` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array()`](array)
-   [`Array.from()`](from)
-   [`TypedArray.of()`](../typedarray/of)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/of>

