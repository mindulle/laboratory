Set.prototype.clear()
=====================

 
The `clear()` method of [`Set`](../set) instances removes all elements
from this set.


 
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


 
### Using the clear() method 

 
 
 
[js]


```js
const mySet = new Set();
mySet.add(1);
mySet.add("foo");

console.log(mySet.size); // 2
console.log(mySet.has("foo")); // true

mySet.clear();

console.log(mySet.size); // 0
console.log(mySet.has("foo")); // false
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-set.prototype.clear]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-set.prototype.clear)

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

 
-   [`Set`](../set)
-   [`Set.prototype.delete()`](delete)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/clear>

