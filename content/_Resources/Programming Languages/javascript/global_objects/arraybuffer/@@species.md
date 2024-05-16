ArrayBuffer\[@\@species\]
=========================


The `ArrayBuffer[@@species]` static accessor property returns the
constructor used to construct return values from array buffer methods.

 
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
ArrayBuffer[Symbol.species]
```





### Return value 


The value of the constructor (`this`) on which `get @@species` was
called. The return value is used to construct return values from array
buffer methods that create new array buffers.




Description
-----------


The `@@species` accessor property returns the default constructor for
`ArrayBuffer` objects. Subclass constructors may override it to change
the constructor assignment. The default implementation is basically:



[js]


```js
// Hypothetical underlying implementation for illustration
class ArrayBuffer {
  static get [Symbol.species]() {
    return this;
  }
}
```


Because of this polymorphic implementation, `@@species` of derived
subclasses would also return the constructor itself by default.



[js]


```js
class SubArrayBuffer extends ArrayBuffer {}
SubArrayBuffer[Symbol.species] === SubArrayBuffer; // true
```


When calling array buffer methods that do not mutate the existing object
but return a new array buffer instance (for example,
[`slice()`](slice)), the object\'s `constructor[@@species]` will be
accessed. The returned constructor will be used to construct the return
value of the array buffer method.




Examples
--------



### Species in ordinary objects 


The `@@species` property returns the default constructor function, which
is the `ArrayBuffer` constructor for `ArrayBuffer`.



[js]


```js
ArrayBuffer[Symbol.species]; // function ArrayBuffer()
```





### Species in derived objects 


In an instance of a custom `ArrayBuffer` subclass, such as
`MyArrayBuffer`, the `MyArrayBuffer` species is the `MyArrayBuffer`
constructor. However, you might want to overwrite this, in order to
return parent `ArrayBuffer` objects in your derived class methods:



[js]


```js
class MyArrayBuffer extends ArrayBuffer {
  // Overwrite MyArrayBuffer species to the parent ArrayBuffer constructor
  static get [Symbol.species]() {
    return ArrayBuffer;
  }
}
```




Specifications
--------------


  --------------------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-arraybuffer-@\@species]](https://tc39.es/ecma262/multipage/structured-data.html#sec-get-arraybuffer-@@species)

  --------------------------------------------------------------------------------------------------------------------------------


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

48

38

10

51

48

41

10

5.0

51

1.0

6.5.0


See also 
--------


-   [`ArrayBuffer`](../arraybuffer)
-   [`Symbol.species`](../symbol/species)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/@@species>

