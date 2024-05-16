SharedArrayBuffer\[@\@species\]
===============================

 
The `SharedArrayBuffer[@@species]` static accessor property returns the
constructor used to construct return values from `SharedArrayBuffer`
methods.

 
**Warning:** The existence of `@@species` allows execution of arbitrary
code and may create security vulnerabilities. It also makes certain
optimizations much harder. Engine implementers are [investigating
whether to remove this
feature](https://github.com/tc39/proposal-rm-builtin-subclassing). Avoid
relying on it if possible.



 
Syntax
------

 
 
 
[js]


```js
SharedArrayBuffer[Symbol.species]
```




 
### Return value 

 
The value of the constructor (`this`) on which `get @@species` was
called. The return value is used to construct return values from array
buffer methods that create new array buffer.



 
Description
-----------

 
The `@@species` accessor property returns the default constructor for
`SharedArrayBuffer` objects. Subclass constructors may override it to
change the constructor assignment. The default implementation is
basically:

 
 
[js]


```js
// Hypothetical underlying implementation for illustration
class SharedArrayBuffer {
  static get [Symbol.species]() {
    return this;
  }
}
```


Because of this polymorphic implementation, `@@species` of derived
subclasses would also return the constructor itself by default.

 
 
[js]


```js
class SubArrayBuffer extends SharedArrayBuffer {}
SubArrayBuffer[Symbol.species] === SharedArrayBuffer; // true
```


When calling array buffer methods that do not mutate the existing array
but return a new array buffer instance (for example,
[`slice()`](slice)), the array\'s `constructor[@@species]` will be
accessed. The returned constructor will be used to construct the return
value of the array buffer method.



 
Examples
--------


 
### Species in ordinary objects 

 
The `@@species` property returns the default constructor function, which
is the `SharedArrayBuffer` constructor for `SharedArrayBuffer`.

 
 
[js]


```js
SharedArrayBuffer[Symbol.species]; // function SharedArrayBuffer()
```




 
### Species in derived objects 

 
In an instance of a custom `SharedArrayBuffer` subclass, such as
`MySharedArrayBuffer`, the `MySharedArrayBuffer` species is the
`MySharedArrayBuffer` constructor. However, you might want to overwrite
this, in order to return parent `SharedArrayBuffer` objects in your
derived class methods:

 
 
[js]


```js
class MySharedArrayBuffer extends SharedArrayBuffer {
  // Overwrite MySharedArrayBuffer species to the parent SharedArrayBuffer constructor
  static get [Symbol.species]() {
    return SharedArrayBuffer;
  }
}
```




Specifications
--------------

 
  ------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-sharedarraybuffer-@\@species]](https://tc39.es/ecma262/multipage/structured-data.html#sec-sharedarraybuffer-@@species)

  ------------------------------------------------------------------------------------------------------------------------------------


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

68

79

79

55

15.2

89

79

63

15.2

15.0

No

1.0

8.10.0

 
See also 
--------

 
-   [`SharedArrayBuffer`](../sharedarraybuffer)
-   [`Symbol.species`](../symbol/species)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer/@@species>

