handler.isExtensible()
======================

 
The `handler.isExtensible()` method is a trap for the `[[IsExtensible]]`
[object internal method](../../proxy#object_internal_methods), which is
used by operations such as
[`Object.isExtensible()`](../../object/isextensible).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Proxy(target, {
  isExtensible(target) {
  }
});
```




 
### Parameters

 
The following parameter is passed to the `isExtensible()` method. `this`
is bound to the handler.

[`target`](#target)

:   The target object.



 
### Return value 

 
The `isExtensible()` method must return a boolean value.



 
Description
-----------


 
### Interceptions

 
This trap can intercept these operations:

-   [`Object.isExtensible()`](../../object/isextensible)
-   [`Reflect.isExtensible()`](../../reflect/isextensible)

Or any other operation that invokes the `[[IsExtensible]]` [internal
method](../../proxy#object_internal_methods).



 
### Invariants

 
If the following invariants are violated, the trap throws a
[`TypeError`](../../typeerror) when invoked.

-   `Object.isExtensible(proxy)` must return the same value as
    `Object.isExtensible(target)`.



 
Examples
--------


 
### Trapping of isExtensible 

 
The following code traps
[`Object.isExtensible()`](../../object/isextensible).

 
 
[js]


```js
const p = new Proxy(
  {},
  {
    isExtensible(target) {
      console.log("called");
      return true;
    },
  },
);

console.log(Object.isExtensible(p));
// "called"
// true
```


The following code violates the invariant.

 
 
[js]


```js
const p = new Proxy(
  {},
  {
    isExtensible(target) {
      return false;
    },
  },
);

Object.isExtensible(p); // TypeError is thrown
```




Specifications
--------------

 
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-proxy-object-internal-methods-and-internal-slots-isextensible]](https://tc39.es/ecma262/multipage/ordinary-and-exotic-objects-behaviours.html#sec-proxy-object-internal-methods-and-internal-slots-isextensible)

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`isExtensible`

49

12

31

36

10

49

31

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
-   [`Object.isExtensible()`](../../object/isextensible)
-   [`Reflect.isExtensible()`](../../reflect/isextensible)
-   [`Reflect.preventExtensions()`](../../reflect/preventextensions)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/isExtensible>

