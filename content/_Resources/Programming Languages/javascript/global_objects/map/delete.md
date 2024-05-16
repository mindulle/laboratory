Map.prototype.delete()
======================

 
The `delete()` method of [`Map`](../map) instances removes the specified
element from this map by key.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
mapInstance.delete(key)
```




 
### Parameters

 

[`key`](#key)

:   The key of the element to remove from the `Map` object.



 
### Return value 

 
`true` if an element in the `Map` object existed and has been removed,
or `false` if the element does not exist.



 
Examples
--------


 
### Using delete() 

 
 
 
[js]


```js
const myMap = new Map();
myMap.set("bar", "foo");

console.log(myMap.delete("bar")); // Returns true. Successfully removed.
console.log(myMap.has("bar")); // Returns false. The "bar" element is no longer present.
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-map.prototype.delete]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-map.prototype.delete)

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

 
-   [`Map`](../map)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/delete>

