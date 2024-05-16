Map.prototype\[@\@iterator\]()
==============================

 
The `[@@iterator]()` method of [`Map`](../map) instances implements the
[iterable protocol](../../iteration_protocols) and allows `Map` objects
to be consumed by most syntaxes expecting iterables, such as the [spread
syntax](../../operators/spread_syntax) and
[`for...of`](../../statements/for...of) loops. It returns a [map
iterator object](../iterator) that yields the key-value pairs of the map
in insertion order.

The initial value of this property is the same function object as the
initial value of the [`Map.prototype.entries`](entries) property.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
map[Symbol.iterator]()
```




 
### Parameters

 
None.



 
### Return value 

 
The same return value as [`Map.prototype.entries()`](entries): a new
[iterable iterator object](../iterator) that yields the key-value pairs
of the map.



 
Examples
--------


 
### Iteration using for\...of loop 

 
Note that you seldom need to call this method directly. The existence of
the `@@iterator` method makes `Map` objects
[iterable](../../iteration_protocols#the_iterable_protocol), and
iterating syntaxes like the `for...of` loop automatically call this
method to obtain the iterator to loop over.

 
 
[js]


```js
const myMap = new Map();
myMap.set("0", "foo");
myMap.set(1, "bar");
myMap.set({}, "baz");

for (const entry of myMap) {
  console.log(entry);
}
// ["0", "foo"]
// [1, "bar"]
// [{}, "baz"]

for (const [key, value] of myMap) {
  console.log(`${key}: ${value}`);
}
// 0: foo
// 1: bar
// [Object]: baz
```




 
### Manually hand-rolling the iterator 

 
You may still manually call the `next()` method of the returned iterator
object to achieve maximum control over the iteration process.

 
 
[js]


```js
const myMap = new Map();
myMap.set("0", "foo");
myMap.set(1, "bar");
myMap.set({}, "baz");

const mapIter = myMap[Symbol.iterator]();

console.log(mapIter.next().value); // ["0", "foo"]
console.log(mapIter.next().value); // [1, "bar"]
console.log(mapIter.next().value); // [Object, "baz"]
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-map.prototype-@\@iterator]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-map.prototype-@@iterator)

  --------------------------------------------------------------------------------------------------------------------------------


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

 
-   [`Map`](../map)
-   [`Map.prototype.entries()`](entries)
-   [`Map.prototype.keys()`](keys)
-   [`Map.prototype.values()`](values)
-   [`Symbol.iterator`](../symbol/iterator)
-   [Iteration protocols](../../iteration_protocols)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/@@iterator>

