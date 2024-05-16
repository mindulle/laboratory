Set.prototype\[@\@iterator\]()
==============================

 
The `[@@iterator]()` method of [`Set`](../set) instances implements the
[iterable protocol](../../iteration_protocols) and allows `Set` objects
to be consumed by most syntaxes expecting iterables, such as the [spread
syntax](../../operators/spread_syntax) and
[`for...of`](../../statements/for...of) loops. It returns a [set
iterator object](../iterator) that yields the values of the set in
insertion order.

The initial value of this property is the same function object as the
initial value of the [`Set.prototype.values`](values) property.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
set[Symbol.iterator]()
```




 
### Parameters

 
None.



 
### Return value 

 
The same return value as [`Set.prototype.values()`](values): a new
[iterable iterator object](../iterator) that yields the values of the
set.



 
Examples
--------


 
### Iteration using for\...of loop 

 
Note that you seldom need to call this method directly. The existence of
the `@@iterator` method makes `Set` objects
[iterable](../../iteration_protocols#the_iterable_protocol), and
iterating syntaxes like the `for...of` loop automatically call this
method to obtain the iterator to loop over.

 
 
[js]


```js
const mySet = new Set();
mySet.add("0");
mySet.add(1);
mySet.add({});

for (const v of mySet) {
  console.log(v);
}
```




 
### Manually hand-rolling the iterator 

 
You may still manually call the `next()` method of the returned iterator
object to achieve maximum control over the iteration process.

 
 
[js]


```js
const mySet = new Set();
mySet.add("0");
mySet.add(1);
mySet.add({});

const setIter = mySet[Symbol.iterator]();

console.log(setIter.next().value); // "0"
console.log(setIter.next().value); // 1
console.log(setIter.next().value); // {}
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-set.prototype-@\@iterator]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-set.prototype-@@iterator)

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

43

12

36

27--36A placeholder property named `@@iterator` is used.

17--27A placeholder property named `iterator` is used.

30

9

43

36

27--36A placeholder property named `@@iterator` is used.

17--27A placeholder property named `iterator` is used.

30

9

4.0

43

1.0

0.12.0

 
See also 
--------

 
-   [`Set`](../set)
-   [`Set.prototype.entries()`](entries)
-   [`Set.prototype.keys()`](keys)
-   [`Set.prototype.values()`](values)
-   [`Symbol.iterator`](../symbol/iterator)
-   [Iteration protocols](../../iteration_protocols)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/@@iterator>

