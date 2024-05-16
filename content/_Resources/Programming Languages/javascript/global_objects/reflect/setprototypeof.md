Reflect.setPrototypeOf()
========================

 
The `Reflect.setPrototypeOf()` static method is like
[`Object.setPrototypeOf()`](../object/setprototypeof) but returns a
[`Boolean`](../boolean). It sets the prototype (i.e., the internal
`[[Prototype]]` property) of a specified object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Reflect.setPrototypeOf(target, prototype)
```




 
### Parameters

 

[`target`](#target)

:   The target object of which to set the prototype.

[`prototype`](#prototype)

:   The object\'s new prototype (an object or
    [`null`](../../operators/null)).



 
### Return value 

 
A [`Boolean`](../boolean) indicating whether or not the prototype was
successfully set.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `target` is not an object or if `prototype` is neither an
    object nor [`null`](../../operators/null).



 
Description
-----------

 
`Reflect.setPrototypeOf()` provides the reflective semantic of setting
the prototype of an object. At the very low level, setting the prototype
returns a boolean (as is the case with [the proxy
handler](../proxy/proxy/setprototypeof)).
[`Object.setPrototypeOf()`](../object/setprototypeof) provides nearly
the same semantic, but it throws a [`TypeError`](../typeerror) if the
status is `false` (the operation was unsuccessful), while
`Reflect.setPrototypeOf()` directly returns the status.

`Reflect.setPrototypeOf()` invokes the `[[SetPrototypeOf]]` [object
internal method](../proxy#object_internal_methods) of `target`.



 
Examples
--------


 
### Using Reflect.setPrototypeOf() 

 
 
 
[js]


```js
Reflect.setPrototypeOf({}, Object.prototype); // true

// It can change an object's [[Prototype]] to null.
Reflect.setPrototypeOf({}, null); // true

// Returns false if target is not extensible.
Reflect.setPrototypeOf(Object.freeze({}), null); // false

// Returns false if it cause a prototype chain cycle.
const target = {};
const proto = Object.create(target);
Reflect.setPrototypeOf(target, proto); // false
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-reflect.setprototypeof]](https://tc39.es/ecma262/multipage/reflection.html#sec-reflect.setprototypeof)

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

`setPrototypeOf`

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

 
-   [Polyfill of `Reflect.setPrototypeOf` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-reflect)
-   [`Reflect`](../reflect)
-   [`Object.setPrototypeOf()`](../object/setprototypeof)
-   [`handler.setPrototypeOf()`](../proxy/proxy/setprototypeof)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/setPrototypeOf>

