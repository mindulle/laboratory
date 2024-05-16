handler.ownKeys()
=================

 
The `handler.ownKeys()` method is a trap for the `[[OwnPropertyKeys]]`
[object internal method](../../proxy#object_internal_methods), which is
used by operations such as [`Object.keys()`](../../object/keys),
[`Reflect.ownKeys()`](../../reflect/ownkeys), etc.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Proxy(target, {
  ownKeys(target) {
  }
});
```




 
### Parameters

 
The following parameter is passed to the `ownKeys()` method. `this` is
bound to the handler.

[`target`](#target)

:   The target object.



 
### Return value 

 
The `ownKeys()` method must return an enumerable object.



 
Description
-----------


 
### Interceptions

 
This trap can intercept these operations:

-   [`Object.getOwnPropertyNames()`](../../object/getownpropertynames)
-   [`Object.getOwnPropertySymbols()`](../../object/getownpropertysymbols)
-   [`Object.keys()`](../../object/keys)
-   [`Reflect.ownKeys()`](../../reflect/ownkeys)

Or any other operation that invokes the `[[OwnPropertyKeys]]` [internal
method](../../proxy#object_internal_methods).



 
### Invariants

 
If the following invariants are violated, the trap throws a
[`TypeError`](../../typeerror) when invoked.

-   The result of `ownKeys()` must be an array.
-   The type of each array element is either a [`String`](../../string)
    or a [`Symbol`](../../symbol).
-   The result List must contain the keys of all non-configurable own
    properties of the target object.
-   If the target object is not extensible, then the result List must
    contain all the keys of the own properties of the target object and
    no other values.



 
Examples
--------


 
### Trapping of getOwnPropertyNames 

 
The following code traps
[`Object.getOwnPropertyNames()`](../../object/getownpropertynames).

 
 
[js]


```js
const p = new Proxy(
  {},
  {
    ownKeys(target) {
      console.log("called");
      return ["a", "b", "c"];
    },
  },
);

console.log(Object.getOwnPropertyNames(p));
// "called"
// [ 'a', 'b', 'c' ]
```


The following code violates an invariant.

 
 
[js]


```js
const obj = {};
Object.defineProperty(obj, "a", {
  configurable: false,
  enumerable: true,
  value: 10,
});

const p = new Proxy(obj, {
  ownKeys(target) {
    return [123, 12.5, true, false, undefined, null, {}, []];
  },
});

console.log(Object.getOwnPropertyNames(p));

// TypeError: proxy [[OwnPropertyKeys]] must return an array
// with only string and symbol elements
```




Specifications
--------------

 
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-proxy-object-internal-methods-and-internal-slots-ownpropertykeys]](https://tc39.es/ecma262/multipage/ordinary-and-exotic-objects-behaviours.html#sec-proxy-object-internal-methods-and-internal-slots-ownpropertykeys)

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`ownKeys`

49

12

18In Firefox 42, the implementation got updated to reflect the final
ES2015 specification: The result is now checked if it is an array and if
the array elements are either of type string or of type symbol.
Enumerating duplicate own property names is not a failure anymore.

36

10

49

18In Firefox 42, the implementation got updated to reflect the final
ES2015 specification: The result is now checked if it is an array and if
the array elements are either of type string or of type symbol.
Enumerating duplicate own property names is not a failure anymore.

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
-   [`Object.getOwnPropertyNames()`](../../object/getownpropertynames)
-   [`Reflect.ownKeys()`](../../reflect/ownkeys)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/ownKeys>

