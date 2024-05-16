Set.prototype.delete()
======================

 
The `delete()` method of [`Set`](../set) instances removes a specified
value from this set, if it is in the set.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
setInstance.delete(value)
```




 
### Parameters

 

[`value`](#value)

:   The value to remove from `Set`.



 
### Return value 

 
Returns `true` if `value` was already in `Set`; otherwise `false`.



 
Examples
--------


 
### Using the delete() method 

 
 
 
[js]


```js
const mySet = new Set();
mySet.add("foo");

console.log(mySet.delete("bar")); // false; no "bar" element found to be deleted.
console.log(mySet.delete("foo")); // true; successfully removed.

console.log(mySet.has("foo")); // false; the "foo" element is no longer present.
```




 
### Deleting an object from a set 

 
Because objects are compared by reference, you have to delete them by
checking individual properties if you don\'t have a reference to the
original object.

 
 
[js]


```js
const setObj = new Set(); // Create a new set.

setObj.add({ x: 10, y: 20 }); // Add object in the set.

setObj.add({ x: 20, y: 30 }); // Add object in the set.

// Delete any point with `x > 10`.
setObj.forEach((point) => {
  if (point.x > 10) {
    setObj.delete(point);
  }
});
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-set.prototype.delete]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-set.prototype.delete)

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

`delete`

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
-   [`Set.prototype.clear()`](clear)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/delete>

