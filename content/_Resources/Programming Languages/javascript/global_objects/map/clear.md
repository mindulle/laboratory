Map.prototype.clear()
=====================

 
The `clear()` method of [`Map`](../map) instances removes all elements
from this map.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
clear()
```




 
### Parameters

 
None.



 
### Return value 

 
None ([`undefined`](../undefined)).



 
Examples
--------


 
### Using clear() 

 
 
 
[js]


```js
const myMap = new Map();
myMap.set("bar", "baz");
myMap.set(1, "foo");

console.log(myMap.size); // 2
console.log(myMap.has("bar")); // true

myMap.clear();

console.log(myMap.size); // 0
console.log(myMap.has("bar")); // false
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-map.prototype.clear]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-map.prototype.clear)

  ---------------------------------------------------------------------------------------------------------------------


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

`clear`

38

12

19

25

8

38

19

25

8

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [`Map`](../map)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/clear>

