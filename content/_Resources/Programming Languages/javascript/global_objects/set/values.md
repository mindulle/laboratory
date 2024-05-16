Set.prototype.values()
======================

 
The `values()` method of [`Set`](../set) instances returns a new *[set
iterator](../iterator)* object that contains the values for each element
in this set in insertion order.


 
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
const mySet = new Set();
mySet.add("foo");
mySet.add("bar");
mySet.add("baz");

const setIter = mySet.values();

console.log(setIter.next().value); // "foo"
console.log(setIter.next().value); // "bar"
console.log(setIter.next().value); // "baz"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-set.prototype.values]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-set.prototype.values)

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

 
-   [`Set.prototype.entries()`](entries)
-   [`Set.prototype.keys()`](keys)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/values>

