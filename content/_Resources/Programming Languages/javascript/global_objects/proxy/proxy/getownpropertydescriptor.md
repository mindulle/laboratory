handler.getOwnPropertyDescriptor()
==================================

 
The `handler.getOwnPropertyDescriptor()` method is a trap for the
`[[GetOwnProperty]]` [object internal
method](../../proxy#object_internal_methods), which is used by
operations such as
[`Object.getOwnPropertyDescriptor()`](../../object/getownpropertydescriptor).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Proxy(target, {
  getOwnPropertyDescriptor(target, prop) {
  }
});
```




 
### Parameters

 
The following parameters are passed to the `getOwnPropertyDescriptor()`
method. `this` is bound to the handler.

[`target`](#target)

:   The target object.

[`prop`](#prop)

:   The name of the property whose description should be retrieved.



 
### Return value 

 
The `getOwnPropertyDescriptor()` method must return an object or
`undefined`.



 
Description
-----------


 
### Interceptions

 
This trap can intercept these operations:

-   [`Object.getOwnPropertyDescriptor()`](../../object/getownpropertydescriptor)
-   [`Reflect.getOwnPropertyDescriptor()`](../../reflect/getownpropertydescriptor)

Or any other operation that invokes the `[[GetOwnProperty]]` [internal
method](../../proxy#object_internal_methods).



 
### Invariants

 
If the following invariants are violated, the trap throws a
[`TypeError`](../../typeerror) when invoked.

-   `getOwnPropertyDescriptor()` must return an object or `undefined`.
-   A property cannot be reported as non-existent, if it exists as a
    non-configurable own property of the target object.
-   A property cannot be reported as non-existent, if it exists as an
    own property of the target object and the target object is not
    extensible.
-   A property cannot be reported as existent, if it does not exists as
    an own property of the target object and the target object is not
    extensible.
-   A property cannot be reported as non-configurable, if it does not
    exists as an own property of the target object or if it exists as a
    configurable own property of the target object.
-   The result of `Object.getOwnPropertyDescriptor(target)` can be
    applied to the target object using `Object.defineProperty()` and
    will not throw an exception.



 
Examples
--------


 
### Trapping of getOwnPropertyDescriptor 

 
The following code traps
[`Object.getOwnPropertyDescriptor()`](../../object/getownpropertydescriptor).

 
 
[js]


```js
const p = new Proxy(
  { a: 20 },
  {
    getOwnPropertyDescriptor(target, prop) {
      console.log(`called: ${prop}`);
      return { configurable: true, enumerable: true, value: 10 };
    },
  },
);

console.log(Object.getOwnPropertyDescriptor(p, "a").value);
// "called: a"
// 10
```


The following code violates an invariant.

 
 
[js]


```js
const obj = { a: 10 };
Object.preventExtensions(obj);
const p = new Proxy(obj, {
  getOwnPropertyDescriptor(target, prop) {
    return undefined;
  },
});

Object.getOwnPropertyDescriptor(p, "a"); // TypeError is thrown
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-proxy-object-internal-methods-and-internal-slots-getownproperty-p]](https://tc39.es/ecma262/multipage/ordinary-and-exotic-objects-behaviours.html#sec-proxy-object-internal-methods-and-internal-slots-getownproperty-p)

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`getOwnPropertyDescriptor`

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

 
-   [`Proxy`](../../proxy)
-   [`Proxy()` constructor](../proxy)
-   [`Object.getOwnPropertyDescriptor()`](../../object/getownpropertydescriptor)
-   [`Reflect.getOwnPropertyDescriptor()`](../../reflect/getownpropertydescriptor)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/getOwnPropertyDescriptor>

