Map.prototype.set()
===================

 
The `set()` method of [`Map`](../map) instances adds or updates an entry
in this map with a specified key and a value.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
set(key, value)
```




 
### Parameters

 

[`key`](#key)

:   The key of the element to add to the `Map` object. The key may be
    any [JavaScript
    type](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
    (any [primitive
    value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#primitive_values)
    or any type of [JavaScript
    object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#objects)).

[`value`](#value)

:   The value of the element to add to the `Map` object. The value may
    be any [JavaScript
    type](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
    (any [primitive
    value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#primitive_values)
    or any type of [JavaScript
    object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#objects)).



 
### Return value 

 
The `Map` object.



 
Examples
--------


 
### Using set() 

 
 
 
[js]


```js
const myMap = new Map();

// Add new elements to the map
myMap.set("bar", "foo");
myMap.set(1, "foobar");

// Update an element in the map
myMap.set("bar", "baz");
```




 
### Using the set() with chaining 

 
Since the `set()` method returns back the same `Map` object, you can
chain the method call like below:

 
 
[js]


```js
// Add new elements to the map with chaining.
myMap.set("bar", "foo").set(1, "foobar").set(2, "baz");
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-map.prototype.set]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-map.prototype.set)

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

`set`

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
-   [`Map.prototype.get()`](get)
-   [`Map.prototype.has()`](has)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/set>

