Map.prototype.values()
======================

 
The `values()` method of [`Map`](../map) instances returns a new *[map
iterator](../iterator)* object that contains the values for each element
in this map in insertion order.


 
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



 
Examples
--------


 
### Using values() 

 
 
 
[js]


```js
const myMap = new Map();
myMap.set("0", "foo");
myMap.set(1, "bar");
myMap.set({}, "baz");

const mapIter = myMap.values();

console.log(mapIter.next().value); // "foo"
console.log(mapIter.next().value); // "bar"
console.log(mapIter.next().value); // "baz"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-map.prototype.values]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-map.prototype.values)

  -----------------------------------------------------------------------------------------------------------------------


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

 
-   [`Map.prototype.entries()`](entries)
-   [`Map.prototype.keys()`](keys)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/values>

