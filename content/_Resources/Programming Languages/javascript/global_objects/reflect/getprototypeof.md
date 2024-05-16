Reflect.getPrototypeOf()
========================

 
The `Reflect.getPrototypeOf()` static method is like
[`Object.getPrototypeOf()`](../object/getprototypeof). It returns the
prototype of the specified object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Reflect.getPrototypeOf(target)
```




 
### Parameters

 

[`target`](#target)

:   The target object of which to get the prototype.



 
### Return value 

 
The prototype of the given object, which may be an object or `null`.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `target` is not an object.



 
Description
-----------

 
`Reflect.getPrototypeOf()` provides the reflective semantic of
retrieving the prototype of an object. The only difference with
[`Object.getPrototypeOf()`](../object/getprototypeof) is how non-object
targets are handled. `Reflect.getPrototypeOf()` throws a
[`TypeError`](../typeerror) if the target is not an object, while
`Object.getPrototypeOf()` coerces it to an object.

`Reflect.getPrototypeOf()` invokes the `[[GetPrototypeOf]]` [object
internal method](../proxy#object_internal_methods) of `target`.



 
Examples
--------


 
### Using Reflect.getPrototypeOf() 

 
 
 
[js]


```js
Reflect.getPrototypeOf({}); // Object.prototype
Reflect.getPrototypeOf(Object.prototype); // null
Reflect.getPrototypeOf(Object.create(null)); // null
```




 
### Difference with Object.getPrototypeOf() 

 
 
 
[js]


```js
// Same result for Objects
Object.getPrototypeOf({}); // Object.prototype
Reflect.getPrototypeOf({}); // Object.prototype

// Both throw in ES5 for non-Objects
Object.getPrototypeOf("foo"); // Throws TypeError
Reflect.getPrototypeOf("foo"); // Throws TypeError

// In ES2015 only Reflect throws, Object coerces non-Objects
Object.getPrototypeOf("foo"); // String.prototype
Reflect.getPrototypeOf("foo"); // Throws TypeError

// To mimic the Object ES2015 behavior you need to coerce
Reflect.getPrototypeOf(Object("foo")); // String.prototype
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-reflect.getprototypeof]](https://tc39.es/ecma262/multipage/reflection.html#sec-reflect.getprototypeof)

  --------------------------------------------------------------------------------------------------------------------


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

`getPrototypeOf`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

 
See also 
--------

 
-   [Polyfill of `Reflect.getPrototypeOf` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-reflect)
-   [`Reflect`](../reflect)
-   [`Object.getPrototypeOf()`](../object/getprototypeof)
-   [`handler.getPrototypeOf()`](../proxy/proxy/getprototypeof)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/getPrototypeOf>

