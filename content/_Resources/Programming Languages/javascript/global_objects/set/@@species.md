Set\[@\@species\]
=================

 
The `Set[@@species]` static accessor property is an unused accessor
property specifying how to copy `Set` objects.


 
Syntax
------

 
 
 
[js]


```js
Set[Symbol.species]
```




 
### Return value 

 
The value of the constructor (`this`) on which `get @@species` was
called. The return value is used to construct copied `Set` instances.



 
Description
-----------

 
The `@@species` accessor property returns the default constructor for
`Set` objects. Subclass constructors may override it to change the
constructor assignment.

 
**Note:** This property is currently unused by all `Set` methods.




 
Examples
--------


 
### Species in ordinary objects 

 
The `@@species` property returns the default constructor function, which
is the `Set` constructor for `Set`.

 
 
[js]


```js
Set[Symbol.species]; // function Set()
```




 
### Species in derived objects 

 
In an instance of a custom `Set` subclass, such as `MySet`, the `MySet`
species is the `MySet` constructor. However, you might want to overwrite
this, in order to return parent `Set` objects in your derived class
methods:

 
 
[js]


```js
class MySet extends Set {
  // Overwrite MySet species to the parent Set constructor
  static get [Symbol.species]() {
    return Set;
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
  sec-get-set-@\@species]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-get-set-@@species)

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

 
-   [`Set`](../set)
-   [`Symbol.species`](../symbol/species)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/@@species>

