Promise\[@\@species\]
=====================

 
The `Promise[@@species]` static accessor property returns the
constructor used to construct return values from promise methods.

 
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
Promise[Symbol.species]
```




 
### Return value 

 
The value of the constructor (`this`) on which `get @@species` was
called. The return value is used to construct return values from promise
chaining methods that create new promises.



 
Description
-----------

 
The `@@species` accessor property returns the default constructor for
`Promise` objects. Subclass constructors may override it to change the
constructor assignment. The default implementation is basically:

 
 
[js]


```js
// Hypothetical underlying implementation for illustration
class Promise {
  static get [Symbol.species]() {
    return this;
  }
}
```


Because of this polymorphic implementation, `@@species` of derived
subclasses would also return the constructor itself by default.

 
 
[js]


```js
class SubPromise extends Promise {}
SubPromise[Symbol.species] === SubPromise; // true
```


Promise chaining methods --- [`then()`](then), [`catch()`](catch), and
[`finally()`](finally) --- return new promise objects. They get the
constructor to construct the new promise through
`this.constructor[@@species]`. If `this.constructor` is `undefined`, or
if `this.constructor[@@species]` is `undefined` or `null`, the default
[`Promise()`](promise) constructor is used. Otherwise, the constructor
returned by `this.constructor[@@species]` is used to construct the new
promise object.



 
Examples
--------


 
### Species in ordinary objects 

 
The `Symbol.species` property returns the default constructor function,
which is the `Promise` constructor for `Promise`.

 
 
[js]


```js
Promise[Symbol.species]; // [Function: Promise]
```




 
### Species in derived objects 

 
In an instance of a custom `Promise` subclass, such as `MyPromise`, the
`MyPromise` species is the `MyPromise` constructor. However, you might
want to override this, in order to return parent `Promise` objects in
your derived class methods.

 
 
[js]


```js
class MyPromise extends Promise {
  // Override MyPromise species to the parent Promise constructor
  static get [Symbol.species]() {
    return Promise;
  }
}
```


By default, promise methods would return promises with the type of the
subclass.

 
 
[js]


```js
class MyPromise extends Promise {
  someValue = 1;
}

console.log(MyPromise.resolve(1).then(() => {}).someValue); // 1
```


By overriding `@@species`, the promise methods will return the base
`Promise` type.

 
 
[js]


```js
class MyPromise extends Promise {
  someValue = 1;
  static get [Symbol.species]() {
    return Promise;
  }
}

console.log(MyPromise.resolve(1).then(() => {}).someValue); // undefined
```




Specifications
--------------

 
  ------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-promise-@\@species]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-get-promise-@@species)

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

51

79

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

 
-   [`Promise`](../promise)
-   [`Symbol.species`](../symbol/species)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/@@species>

