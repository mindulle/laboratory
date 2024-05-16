Proxy() constructor
===================

 
The `Proxy()` constructor creates [`Proxy`](../proxy) objects.


 
Syntax
------

 
 
 
[js]


```js
new Proxy(target, handler)
```


 
**Note:** `Proxy()` can only be constructed with
[`new`](../../operators/new). Attempting to call it without `new` throws
a [`TypeError`](../typeerror).




 
### Parameters

 

[`target`](#target)

:   A target object to wrap with `Proxy`. It can be any sort of object,
    including a native array, a function, or even another proxy.

[`handler`](#handler)

:   An object whose properties are functions that define the behavior of
    the proxy when an operation is performed on it.



 
Description
-----------

 
Use the `Proxy()` constructor to create a new `Proxy` object. This
constructor takes two mandatory arguments:

-   `target` is the object for which you want to create the proxy
-   `handler` is the object that defines the custom behavior of the
    proxy.

An empty handler will create a proxy that behaves, in almost all
respects, exactly like the target. By defining any of a set group of
functions on the `handler` object, you can customize specific aspects of
the proxy\'s behavior. For example, by defining `get()` you can provide
a customized version of the target\'s [property
accessor](../../operators/property_accessors).



 
### Handler functions 

 
This section lists all the handler functions you can define. Handler
functions are sometimes called *traps*, because they trap calls to the
underlying target object.

[`handler.apply()`](proxy/apply)

:   A trap for a function call.

[`handler.construct()`](proxy/construct)

:   A trap for the [`new`](../../operators/new) operator.

[`handler.defineProperty()`](proxy/defineproperty)

:   A trap for [`Object.defineProperty`](../object/defineproperty).

[`handler.deleteProperty()`](proxy/deleteproperty)

:   A trap for the [`delete`](../../operators/delete) operator.

[`handler.get()`](proxy/get)

:   A trap for getting property values.

[`handler.getOwnPropertyDescriptor()`](proxy/getownpropertydescriptor)

:   A trap for
    [`Object.getOwnPropertyDescriptor`](../object/getownpropertydescriptor).

[`handler.getPrototypeOf()`](proxy/getprototypeof)

:   A trap for [`Object.getPrototypeOf`](../object/getprototypeof).

[`handler.has()`](proxy/has)

:   A trap for the [`in`](../../operators/in) operator.

[`handler.isExtensible()`](proxy/isextensible)

:   A trap for [`Object.isExtensible`](../object/isextensible).

[`handler.ownKeys()`](proxy/ownkeys)

:   A trap for
    [`Object.getOwnPropertyNames`](../object/getownpropertynames) and
    [`Object.getOwnPropertySymbols`](../object/getownpropertysymbols).

[`handler.preventExtensions()`](proxy/preventextensions)

:   A trap for
    [`Object.preventExtensions`](../object/preventextensions).

[`handler.set()`](proxy/set)

:   A trap for setting property values.

[`handler.setPrototypeOf()`](proxy/setprototypeof)

:   A trap for [`Object.setPrototypeOf`](../object/setprototypeof).



 
Examples
--------


 
### Selectively proxy property accessors 

 
In this example the target has two properties, `notProxied` and
`proxied`. We define a handler that returns a different value for
`proxied`, and lets any other accesses through to the target.

 
 
[js]


```js
const target = {
  notProxied: "original value",
  proxied: "original value",
};

const handler = {
  get(target, prop, receiver) {
    if (prop === "proxied") {
      return "replaced value";
    }
    return Reflect.get(...arguments);
  },
};

const proxy = new Proxy(target, handler);

console.log(proxy.notProxied); // "original value"
console.log(proxy.proxied); // "replaced value"
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-proxy-constructor]](https://tc39.es/ecma262/multipage/reflection.html#sec-proxy-constructor)

  ----------------------------------------------------------------------------------------------------------


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

`Proxy`

49

12

18

36

10

49

18

36

10

5.0

49

1.0

6.0.0

 
See also 
--------

 
-   [Meta
    programming](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Meta_programming)
    guide
-   [`Reflect`](../reflect)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy>

