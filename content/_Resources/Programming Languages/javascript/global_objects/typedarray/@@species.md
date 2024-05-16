TypedArray\[@\@species\]
========================

 
The `TypedArray[@@species]` static accessor property returns the
constructor used to construct return values from typed array methods.

 
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
TypedArray[Symbol.species]
```




 
### Return value 

 
The value of the constructor (`this`) on which `get @@species` was
called. The return value is used to construct return values from typed
array methods that create new typed arrays.



 
Description
-----------

 
The `@@species` accessor property returns the default constructor for
[typed array](../typedarray#typedarray_objects) objects. Subclass
constructors may override it to change the constructor assignment. The
default implementation is basically:

 
 
[js]


```js
// Hypothetical underlying implementation for illustration
class TypedArray {
  static get [Symbol.species]() {
    return this;
  }
}
```


Because of this polymorphic implementation, `@@species` of derived
subclasses would also return the constructor itself by default.

 
 
[js]


```js
class SubTypedArray extends Int8Array {}
SubTypedArray[Symbol.species] === SubTypedArray; // true
```


When calling typed array methods that do not mutate the existing array
but return a new array instance (for example, [`filter()`](filter) and
[`map()`](map)), the array\'s `constructor[@@species]` will be accessed.
The returned constructor will be used to construct the return value of
the typed array method.

However, unlike [`Array[@@species]`](../array/@@species), when using
`@@species` to create new typed arrays, the language will make sure that
the newly created array is a proper typed array and has the same content
type as the original array --- for example, you can\'t create a
[`BigInt64Array`](../bigint64array) from a
[`Float64Array`](../float64array), or create a non-BigInt array from a
BigInt array. Doing so throws a [`TypeError`](../typeerror).

 
 
[js]


```js
class BadArray extends Int8Array {
  static get [Symbol.species]() {
    return Array;
  }
}
new BadArray(1).map(() => 0); // TypeError: Method %TypedArray%.prototype.map called on incompatible receiver [object Array]

class BadArray2 extends Int8Array {
  static get [Symbol.species]() {
    return BigInt64Array;
  }
}
new BadArray2(1).map(() => 0n); // TypeError: TypedArray.prototype.map constructed typed array of different content type from |this|
```


 
**Note:** Due to a bug in both [SpiderMonkey](https://bugzil.la/1640194)
and V8, the content type match is not checked. Only Safari will throw a
[`TypeError`](../typeerror) in the second example.




 
Examples
--------


 
### Species in ordinary objects 

 
The `@@species` property returns the default constructor function, which
is one of the typed array constructors itself for any given [typed
array](../typedarray#typedarray_objects) constructor.

 
 
[js]


```js
Int8Array[Symbol.species]; // function Int8Array()
Uint8Array[Symbol.species]; // function Uint8Array()
Float32Array[Symbol.species]; // function Float32Array()
```




 
### Species in derived objects 

 
In an instance of a custom `TypedArray` subclass, such as
`MyTypedArray`, the `MyTypedArray` species is the `MyTypedArray`
constructor. However, you might want to overwrite this, in order to
return a parent [typed array](../typedarray#typedarray_objects) object
in your derived class methods:

 
 
[js]


```js
class MyTypedArray extends Uint8Array {
  // Overwrite MyTypedArray species to the parent Uint8Array constructor
  static get [Symbol.species]() {
    return Uint8Array;
  }
}
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-get-%typedarray%-@\@species]](#)

  -----------------------------------------------------------------------


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

 
-   [`TypedArray`](../typedarray)
-   [`Symbol.species`](../symbol/species)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/@@species>

