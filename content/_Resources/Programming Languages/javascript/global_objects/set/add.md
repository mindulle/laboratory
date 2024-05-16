Set.prototype.add()
===================

 
The `add()` method of [`Set`](../set) instances inserts a new element
with a specified value in to this set, if there isn\'t an element with
the same value already in this set


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
add(value)
```




 
### Parameters

 

[`value`](#value)

:   The value of the element to add to the `Set` object.



 
### Return value 

 
The `Set` object with added value.



 
Examples
--------


 
### Using the add() method 

 
 
 
[js]


```js
const mySet = new Set();

mySet.add(1);
mySet.add(5).add("some text"); // chainable

console.log(mySet);
// Set [1, 5, "some text"]
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-set.prototype.add]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-set.prototype.add)

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

`add`

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
-   [`Set.prototype.delete()`](delete)
-   [`Set.prototype.has()`](has)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/add>

