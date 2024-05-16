Set.prototype.entries()
=======================

 
The `entries()` method of [`Set`](../set) instances returns a new *[set
iterator](../iterator)* object that contains `[value, value]` for each
element in this set, in insertion order. For `Set` objects there is no
`key` like in `Map` objects. However, to keep the API similar to the
`Map` object, each *entry* has the same value for its *key* and *value*
here, so that an array `[value, value]` is returned.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
entries()
```




 
### Parameters

 
None.



 
### Return value 

 
A new [iterable iterator object](../iterator).



 
Examples
--------


 
### Using entries() 

 
 
 
[js]


```js
const mySet = new Set();
mySet.add("foobar");
mySet.add(1);
mySet.add("baz");

const setIter = mySet.entries();

console.log(setIter.next().value); // ["foobar", "foobar"]
console.log(setIter.next().value); // [1, 1]
console.log(setIter.next().value); // ["baz", "baz"]
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-set.prototype.entries]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-set.prototype.entries)

  -------------------------------------------------------------------------------------------------------------------------


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

`entries`

38

12

24

25

8

38

24

25

8

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [`Set.prototype.keys()`](keys)
-   [`Set.prototype.values()`](values)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/entries>

