Array.prototype.toString()
==========================


The `toString()` method of [`Array`](../array) instances returns a
string representing the specified array and its elements.



Try it 
------






Syntax
------




[js]


```js
toString()
```





### Parameters


None.




### Return value 


A string representing the elements of the array.




Description
-----------


The [`Array`](../array) object overrides the `toString` method of
[`Object`](../object). The `toString` method of arrays calls
[`join()`](join) internally, which joins the array and returns one
string containing each array element separated by commas. If the `join`
method is unavailable or is not a function,
[`Object.prototype.toString`](../object/tostring) is used instead,
returning `[object Array]`.



[js]


```js
const arr = [];
arr.join = 1; // re-assign `join` with a non-function
console.log(arr.toString()); // [object Array]

console.log(Array.prototype.toString.call({ join: () => 1 })); // 1
```


JavaScript calls the `toString` method automatically when an array is to
be represented as a text value or when an array is referred to in a
string concatenation.

`Array.prototype.toString` recursively converts each element, including
other arrays, to strings. Because the string returned by
`Array.prototype.toString` does not have delimiters, nested arrays look
like they are flattened.



[js]


```js
const matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
];

console.log(matrix.toString()); // 1,2,3,4,5,6,7,8,9
```


When an array is cyclic (it contains an element that is itself),
browsers avoid infinite recursion by ignoring the cyclic reference.



[js]


```js
const arr = [];
arr.push(1, [3, arr, 4], 2);
console.log(arr.toString()); // 1,3,,4,2
```





Examples
--------



### Using toString() 




[js]


```js
const array1 = [1, 2, "a", "1a"];

console.log(array1.toString()); // "1,2,a,1a"
```





### Using toString() on sparse arrays 


Following the behavior of `join()`, `toString()` treats empty slots the
same as `undefined` and produces an extra separator:



[js]


```js
console.log([1, , 3].toString()); // '1,,3'
```





### Calling toString() on non-array objects 


`toString()` is [generic](../array#generic_array_methods). It expects
`this` to have a `join()` method; or, failing that, uses
`Object.prototype.toString()` instead.



[js]


```js
console.log(Array.prototype.toString.call({ join: () => 1 }));
// 1; a number
console.log(Array.prototype.toString.call({ join: () => undefined }));
// undefined
console.log(Array.prototype.toString.call({ join: "not function" }));
// "[object Object]"
```




Specifications
--------------


  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.tostring]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.tostring)

  ---------------------------------------------------------------------------------------------------------------------------------


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

`toString`

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
-   [`Array.prototype.join()`](join)
-   [`Array.prototype.toLocaleString()`](tolocalestring)
-   [`TypedArray.prototype.toString()`](../typedarray/tostring)
-   [`String.prototype.toString()`](../string/tostring)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toString>

