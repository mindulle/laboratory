Reflect.get()
=============

 
The `Reflect.get()` static method is like the [property
accessor](../../operators/property_accessors) syntax, but as a function.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Reflect.get(target, propertyKey)
Reflect.get(target, propertyKey, receiver)
```




 
### Parameters

 

[`target`](#target)

:   The target object on which to get the property.

[`propertyKey`](#propertykey)

:   The name of the property to get.

[`receiver`](#receiver) [Optional]

:   The value of `this` provided for the call to `target` if a getter is
    encountered.



 
### Return value 

 
The value of the property.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `target` is not an object.



 
Description
-----------

 
`Reflect.get()` provides the reflective semantic of a [property
access](../../operators/property_accessors). That is,
`Reflect.get(target, propertyKey, receiver)` is semantically equivalent
to:

 
 
[js]


```js
target[propertyKey];
```


Note that in a normal property access, `target` and `receiver` would
observably be the same object.

`Reflect.get()` invokes the `[[Get]]` [object internal
method](../proxy#object_internal_methods) of `target`.



 
Examples
--------


 
### Using Reflect.get() 

 
 
 
[js]


```js
// Object
const obj1 = { x: 1, y: 2 };
Reflect.get(obj1, "x"); // 1

// Array
Reflect.get(["zero", "one"], 1); // "one"

// Proxy with a get handler
const obj2 = new Proxy(
  { p: 1 },
  {
    get(t, k, r) {
      return k + "bar";
    },
  },
);
Reflect.get(obj2, "foo"); // "foobar"

// Proxy with get handler and receiver
const obj3 = new Proxy(
  { p: 1, foo: 2 },
  {
    get(t, prop, receiver) {
      return receiver[prop] + "bar";
    },
  },
);
Reflect.get(obj3, "foo", { foo: 3 }); // "3bar"
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-reflect.get]](https://tc39.es/ecma262/multipage/reflection.html#sec-reflect.get)

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

`get`

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

 
-   [Polyfill of `Reflect.get` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-reflect)
-   [`Reflect`](../reflect)
-   [Property accessors](../../operators/property_accessors)
-   [`handler.get()`](../proxy/proxy/get)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/get>

