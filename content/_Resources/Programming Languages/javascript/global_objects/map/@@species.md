Map\[@\@species\]
=================

 
The `Map[@@species]` static accessor property is an unused accessor
property specifying how to copy `Map` objects.


 
Syntax
------

 
 
 
[js]


```js
Map[Symbol.species]
```




 
### Return value 

 
The value of the constructor (`this`) on which `get @@species` was
called. The return value is used to construct copied `Map` instances.



 
Description
-----------

 
The `@@species` accessor property returns the default constructor for
`Map` objects. Subclass constructors may override it to change the
constructor assignment.

 
**Note:** This property is currently unused by all `Map` methods.




 
Examples
--------


 
### Species in ordinary objects 

 
The `@@species` property returns the default constructor function, which
is the `Map` constructor for `Map`.

 
 
[js]


```js
Map[Symbol.species]; // function Map()
```




 
### Species in derived objects 

 
In an instance of a custom `Map` subclass, such as `MyMap`, the `MyMap`
species is the `MyMap` constructor. However, you might want to overwrite
this, in order to return parent `Map` objects in your derived class
methods:

 
 
[js]


```js
class MyMap extends Map {
  // Overwrite MyMap species to the parent Map constructor
  static get [Symbol.species]() {
    return Map;
  }
}
```




Specifications
--------------

 
  ------------------------------------------------------------------------------------------------------------------
  Specification
  ------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-map-@\@species]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-get-map-@@species)

  ------------------------------------------------------------------------------------------------------------------


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

`@@species`

51

13

41

38

10

51

41

41

10

5.0

51

1.0

6.5.0

 
See also 
--------

 
-   [`Map`](../map)
-   [`Symbol.species`](../symbol/species)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/@@species>

