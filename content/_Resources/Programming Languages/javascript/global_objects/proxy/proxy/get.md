handler.get()
=============

 
The `handler.get()` method is a trap for the `[[Get]]` [object internal
method](../../proxy#object_internal_methods), which is used by
operations such as [property
accessors](../../../operators/property_accessors).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Proxy(target, {
  get(target, property, receiver) {
  }
});
```




 
### Parameters

 
The following parameters are passed to the `get()` method. `this` is
bound to the handler.

[`target`](#target)

:   The target object.

[`property`](#property)

:   The name or [`Symbol`](../../symbol) of the property to get.

[`receiver`](#receiver)

:   Either the proxy or an object that inherits from the proxy.



 
### Return value 

 
The `get()` method can return any value.



 
Description
-----------


 
### Interceptions

 
This trap can intercept these operations:

-   Property access: `proxy[foo]` and `proxy.bar`
-   [`Reflect.get()`](../../reflect/get)

Or any other operation that invokes the `[[Get]]` [internal
method](../../proxy#object_internal_methods).



 
### Invariants

 
If the following invariants are violated, the trap throws a
[`TypeError`](../../typeerror) when invoked.

-   The value reported for a property must be the same as the value of
    the corresponding target object property if the target object
    property is a non-writable, non-configurable own data property.
-   The value reported for a property must be undefined if the
    corresponding target object property is a non-configurable own
    accessor property that has `undefined` as its `[[Get]]` attribute.



 
Examples
--------


 
### Trap for getting a property value 

 
The following code traps getting a property value.

 
 
[js]


```js
const p = new Proxy(
  {},
  {
    get(target, property, receiver) {
      console.log(`called: ${property}`);
      return 10;
    },
  },
);

console.log(p.a);
// "called: a"
// 10
```


The following code violates an invariant.

 
 
[js]


```js
const obj = {};
Object.defineProperty(obj, "a", {
  configurable: false,
  enumerable: false,
  value: 10,
  writable: false,
});

const p = new Proxy(obj, {
  get(target, property) {
    return 20;
  },
});

p.a; // TypeError is thrown
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-proxy-object-internal-methods-and-internal-slots-get-p-receiver]](https://tc39.es/ecma262/multipage/ordinary-and-exotic-objects-behaviours.html#sec-proxy-object-internal-methods-and-internal-slots-get-p-receiver)

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

`get`

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
-   [`Reflect.get()`](../../reflect/get)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/get>

