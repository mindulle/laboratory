Map.prototype.get()
===================

 
The `get()` method of [`Map`](../map) instances returns a specified
element from this map. If the value that is associated to the provided
key is an object, then you will get a reference to that object and any
change made to that object will effectively modify it inside the `Map`
object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
get(key)
```




 
### Parameters

 

[`key`](#key)

:   The key of the element to return from the `Map` object.



 
### Return value 

 
The element associated with the specified key, or
[`undefined`](../undefined) if the key can\'t be found in the `Map`
object.



 
Examples
--------


 
### Using get() 

 
 
 
[js]


```js
const myMap = new Map();
myMap.set("bar", "foo");

console.log(myMap.get("bar")); // Returns "foo"
console.log(myMap.get("baz")); // Returns undefined
```




 
### Using get() to retrieve a reference to an object 

 
 
 
[js]


```js
const arr = [];
const myMap = new Map();
myMap.set("bar", arr);

myMap.get("bar").push("foo");

console.log(arr); // ["foo"]
console.log(myMap.get("bar")); // ["foo"]
```


Note that the map holding a reference to the original object effectively
means the object cannot be garbage-collected, which may lead to
unexpected memory issues. If you want the object stored in the map to
have the same lifespan as the original one, consider using a
[`WeakMap`](../weakmap).



Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-map.prototype.get]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-map.prototype.get)

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

`get`

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
-   [`Map.prototype.has()`](has)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/get>

