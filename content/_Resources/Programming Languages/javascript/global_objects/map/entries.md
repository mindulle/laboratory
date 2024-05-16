Map.prototype.entries()
=======================

 
The `entries()` method of [`Map`](../map) instances returns a new *[map
iterator](../iterator)* object that contains the `[key, value]` pairs
for each element in this map in insertion order.


 
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
const myMap = new Map();
myMap.set("0", "foo");
myMap.set(1, "bar");
myMap.set({}, "baz");

const mapIter = myMap.entries();

console.log(mapIter.next().value); // ["0", "foo"]
console.log(mapIter.next().value); // [1, "bar"]
console.log(mapIter.next().value); // [Object, "baz"]
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-map.prototype.entries]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-map.prototype.entries)

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

20

25

8

38

20

25

8

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [`Map.prototype.keys()`](keys)
-   [`Map.prototype.values()`](values)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/entries>

