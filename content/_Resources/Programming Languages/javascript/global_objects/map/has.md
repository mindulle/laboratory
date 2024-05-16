Map.prototype.has()
===================

 
The `has()` method of [`Map`](../map) instances returns a boolean
indicating whether an element with the specified key exists in this map
or not.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
has(key)
```




 
### Parameters

 

[`key`](#key)

:   The key of the element to test for presence in the `Map` object.



 
### Return value 

 
`true` if an element with the specified key exists in the `Map` object;
otherwise `false`.



 
Examples
--------


 
### Using has() 

 
 
 
[js]


```js
const myMap = new Map();
myMap.set("bar", "foo");

console.log(myMap.has("bar")); // true
console.log(myMap.has("baz")); // false
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-map.prototype.has]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-map.prototype.has)

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

 
-   [`Map`](../map)
-   [`Map.prototype.set()`](set)
-   [`Map.prototype.get()`](get)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/has>

