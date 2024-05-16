Map.prototype.size
==================

 
The `size` accessor property of [`Map`](../map) instances returns the
number of elements in this map.


 
Try it 
------

 



 
Description
-----------

 
The value of `size` is an integer representing how many entries the
`Map` object has. A set accessor function for `size` is `undefined`; you
can not change this property.



 
Examples
--------


 
### Using size 

 
 
 
[js]


```js
const myMap = new Map();
myMap.set("a", "alpha");
myMap.set("b", "beta");
myMap.set("g", "gamma");

console.log(myMap.size); // 3
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-map.prototype.size]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-get-map.prototype.size)

  ---------------------------------------------------------------------------------------------------------------------------


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

`size`

38

12

19From Firefox 13 to Firefox 18, the `size` property was implemented as
a `Map.prototype.size()` method, this has been changed to a property in
later versions conform to the ECMAScript 2015 specification.

25

8

38

19From Firefox 13 to Firefox 18, the `size` property was implemented as
a `Map.prototype.size()` method, this has been changed to a property in
later versions conform to the ECMAScript 2015 specification.

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/size>

