Set.prototype.size
==================

 
The `size` accessor property of [`Set`](../set) instances returns the
number of (unique) elements in this set.


 
Try it 
------

 



 
Description
-----------

 
The value of `size` is an integer representing how many entries the
`Set` object has. A set accessor function for `size` is `undefined`; you
cannot change this property.



 
Examples
--------


 
### Using size 

 
 
 
[js]


```js
const mySet = new Set();
mySet.add(1);
mySet.add(5);
mySet.add("some text");

console.log(mySet.size); // 3
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-set.prototype.size]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-get-set.prototype.size)

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
a `Set.prototype.size()` method, this has been changed to a property in
later versions conform to the ECMAScript 2015 specification.

25

8

38

19From Firefox 13 to Firefox 18, the `size` property was implemented as
a `Set.prototype.size()` method, this has been changed to a property in
later versions conform to the ECMAScript 2015 specification.

25

8

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [`Set`](../set)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/size>

