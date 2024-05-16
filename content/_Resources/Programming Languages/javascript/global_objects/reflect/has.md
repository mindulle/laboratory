Reflect.has()
=============

 
The `Reflect.has()` static method is like the [`in`](../../operators/in)
operator, but as a function.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Reflect.has(target, propertyKey)
```




 
### Parameters

 

[`target`](#target)

:   The target object in which to look for the property.

[`propertyKey`](#propertykey)

:   The name of the property to check.



 
### Return value 

 
A [`Boolean`](../boolean) indicating whether or not the `target` has the
property.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `target` is not an object.



 
Description
-----------

 
`Reflect.has()` provides the reflective semantic of checking if a
property is in an object. That is, `Reflect.has(target, propertyKey)` is
semantically equivalent to:

 
 
[js]


```js
propertyKey in target;
```


`Reflect.has()` invokes the `[[HasProperty]]` [object internal
method](../proxy#object_internal_methods) of `target`.



 
Examples
--------


 
### Using Reflect.has() 

 
 
 
[js]


```js
Reflect.has({ x: 0 }, "x"); // true
Reflect.has({ x: 0 }, "y"); // false

// returns true for properties in the prototype chain
Reflect.has({ x: 0 }, "toString");

// Proxy with .has() handler method
obj = new Proxy(
  {},
  {
    has(t, k) {
      return k.startsWith("door");
    },
  },
);
Reflect.has(obj, "doorbell"); // true
Reflect.has(obj, "dormitory"); // false
```


`Reflect.has` returns `true` for any inherited properties, like the
[`in`](../../operators/in) operator:

 
 
[js]


```js
const a = { foo: 123 };
const b = { __proto__: a };
const c = { __proto__: b };
// The prototype chain is: c -> b -> a
Reflect.has(c, "foo"); // true
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-reflect.has]](https://tc39.es/ecma262/multipage/reflection.html#sec-reflect.has)

  ----------------------------------------------------------------------------------------------


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

`has`

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

 
-   [Polyfill of `Reflect.has` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-reflect)
-   [`Reflect`](../reflect)
-   [`in`](../../operators/in)
-   [`handler.has()`](../proxy/proxy/has)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/has>

