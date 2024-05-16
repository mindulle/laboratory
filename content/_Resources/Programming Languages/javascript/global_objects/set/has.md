Set.prototype.has()
===================

 
The `has()` method of [`Set`](../set) instances returns a boolean
indicating whether an element with the specified value exists in this
set or not.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
has(value)
```




 
### Parameters

 

[`value`](#value)

:   The value to test for presence in the `Set` object.



 
### Return value 

 
Returns `true` if an element with the specified value exists in the
`Set` object; otherwise `false`.



 
Examples
--------


 
### Using the has() method 

 
 
 
[js]


```js
const mySet = new Set();
mySet.add("foo");

console.log(mySet.has("foo")); // true
console.log(mySet.has("bar")); // false

const set1 = new Set();
const obj1 = { key1: 1 };
set1.add(obj1);

console.log(set1.has(obj1)); // true
console.log(set1.has({ key1: 1 })); // false, because they are different object references
console.log(set1.add({ key1: 1 })); // now set1 contains 2 entries
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-set.prototype.has]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-set.prototype.has)

  -----------------------------------------------------------------------------------------------------------------


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

`has`

38

12

13

25

8

38

14

25

8

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [`Set`](../set)
-   [`Set.prototype.add()`](add)
-   [`Set.prototype.delete()`](delete)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/has>

