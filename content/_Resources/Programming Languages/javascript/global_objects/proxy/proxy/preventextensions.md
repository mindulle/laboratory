handler.preventExtensions()
===========================

 
The `handler.preventExtensions()` method is a trap for the
`[[PreventExtensions]]` [object internal
method](../../proxy#object_internal_methods), which is used by
operations such as
[`Object.preventExtensions()`](../../object/preventextensions).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Proxy(target, {
  preventExtensions(target) {
  }
});
```




 
### Parameters

 
The following parameter is passed to the `preventExtensions()` method.
`this` is bound to the handler.

[`target`](#target)

:   The target object.



 
### Return value 

 
The `preventExtensions()` method must return a boolean value.



 
Description
-----------


 
### Interceptions

 
This trap can intercept these operations:

-   [`Object.preventExtensions()`](../../object/preventextensions)
-   [`Reflect.preventExtensions()`](../../reflect/preventextensions)
-   [`Object.seal()`](../../object/seal)
-   [`Object.freeze()`](../../object/freeze)

Or any other operation that invokes the `[[PreventExtensions]]`
[internal method](../../proxy#object_internal_methods).



 
### Invariants

 
If the following invariants are violated, the trap throws a
[`TypeError`](../../typeerror) when invoked.

-   `Object.preventExtensions(proxy)` only returns `true` if
    `Object.isExtensible(proxy)` is `false`.



 
Examples
--------


 
### Trapping of preventExtensions 

 
The following code traps
[`Object.preventExtensions()`](../../object/preventextensions).

 
 
[js]


```js
const p = new Proxy(
  {},
  {
    preventExtensions(target) {
      console.log("called");
      Object.preventExtensions(target);
      return true;
    },
  },
);

console.log(Object.preventExtensions(p));
// "called"
// false
```


The following code violates the invariant.

 
 
[js]


```js
const p = new Proxy(
  {},
  {
    preventExtensions(target) {
      return true;
    },
  },
);

Object.preventExtensions(p); // TypeError is thrown
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-proxy-object-internal-methods-and-internal-slots-preventextensions]](https://tc39.es/ecma262/multipage/ordinary-and-exotic-objects-behaviours.html#sec-proxy-object-internal-methods-and-internal-slots-preventextensions)

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`preventExtensions`

49

12

22

36

10

49

22

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
-   [`Object.preventExtensions()`](../../object/preventextensions)
-   [`Reflect.preventExtensions()`](../../reflect/preventextensions)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/preventExtensions>

