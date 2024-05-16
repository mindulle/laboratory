handler.getPrototypeOf()
========================

 
The `handler.getPrototypeOf()` method is a trap for the
`[[GetPrototypeOf]]` [object internal
method](../../proxy#object_internal_methods), which is used by
operations such as
[`Object.getPrototypeOf()`](../../object/getprototypeof).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Proxy(obj, {
  getPrototypeOf(target) {
    // …
  }
});
```




 
### Parameters

 
The following parameter is passed to the `getPrototypeOf()` method.
`this` is bound to the handler.

[`target`](#target)

:   The target object.



 
### Return value 

 
The `getPrototypeOf()` method must return an object or `null`.



 
Description
-----------


 
### Interceptions

 
This trap can intercept these operations:

-   [`Object.getPrototypeOf()`](../../object/getprototypeof)
-   [`Reflect.getPrototypeOf()`](../../reflect/getprototypeof)
-   [`__proto__`](../../object/proto)
-   [`Object.prototype.isPrototypeOf()`](../../object/isprototypeof)
-   [`instanceof`](../../../operators/instanceof)

Or any other operation that invokes the `[[GetPrototypeOf]]` [internal
method](../../proxy#object_internal_methods).



 
### Invariants

 
If the following invariants are violated, the trap throws a
[`TypeError`](../../typeerror) when invoked.

-   `getPrototypeOf()` method must return an object or `null`.
-   If `target` is not extensible, `Object.getPrototypeOf(proxy)` method
    must return the same value as `Object.getPrototypeOf(target)`.



 
Examples
--------


 
### Basic usage 

 
 
 
[js]


```js
const obj = {};
const proto = {};
const handler = {
  getPrototypeOf(target) {
    console.log(target === obj); // true
    console.log(this === handler); // true
    return proto;
  },
};

const p = new Proxy(obj, handler);
console.log(Object.getPrototypeOf(p) === proto); // true
```




 
### Five ways to trigger the getPrototypeOf trap 

 
 
 
[js]


```js
const obj = {};
const p = new Proxy(obj, {
  getPrototypeOf(target) {
    return Array.prototype;
  },
});
console.log(
  Object.getPrototypeOf(p) === Array.prototype, // true
  Reflect.getPrototypeOf(p) === Array.prototype, // true
  p.__proto__ === Array.prototype, // true
  Array.prototype.isPrototypeOf(p), // true
  p instanceof Array, // true
);
```




 
### Two kinds of exceptions 

 
 
 
[js]


```js
const obj = {};
const p = new Proxy(obj, {
  getPrototypeOf(target) {
    return "foo";
  },
});
Object.getPrototypeOf(p); // TypeError: "foo" is not an object or null

const obj2 = Object.preventExtensions({});
const p2 = new Proxy(obj2, {
  getPrototypeOf(target) {
    return {};
  },
});
Object.getPrototypeOf(p2); // TypeError: expected same prototype value
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-proxy-object-internal-methods-and-internal-slots-getprototypeof]](https://tc39.es/ecma262/multipage/ordinary-and-exotic-objects-behaviours.html#sec-proxy-object-internal-methods-and-internal-slots-getprototypeof)

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

79

49

36

10

49

49

36

10

5.0

49

1.0

6.0.0

 
See also 
--------

 
-   [`Proxy`](../../proxy)
-   [`Proxy()` constructor](../proxy)
-   [`Object.getPrototypeOf()`](../../object/getprototypeof)
-   [`Reflect.getPrototypeOf()`](../../reflect/getprototypeof)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/getPrototypeOf>

