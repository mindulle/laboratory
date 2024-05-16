handler.defineProperty()
========================

 
The `handler.defineProperty()` method is a trap for the
`[[DefineOwnProperty]]` [object internal
method](../../proxy#object_internal_methods), which is used by
operations such as
[`Object.defineProperty()`](../../object/defineproperty).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Proxy(target, {
  defineProperty(target, property, descriptor) {
  }
});
```




 
### Parameters

 
The following parameters are passed to the `defineProperty()` method.
`this` is bound to the handler.

[`target`](#target)

:   The target object.

[`property`](#property)

:   The name or [`Symbol`](../../symbol) of the property whose
    description is to be retrieved.

[`descriptor`](#descriptor)

:   The descriptor for the property being defined or modified.



 
### Return value 

 
The `defineProperty()` method must return a [`Boolean`](../../boolean)
indicating whether or not the property has been successfully defined.



 
Description
-----------


 
### Interceptions

 
This trap can intercept these operations:

-   [`Object.defineProperty()`](../../object/defineproperty),
    [`Object.defineProperties()`](../../object/defineproperties)
-   [`Reflect.defineProperty()`](../../reflect/defineproperty)

Or any other operation that invokes the `[[DefineOwnProperty]]`
[internal method](../../proxy#object_internal_methods).



 
### Invariants

 
If the following invariants are violated, the trap throws a
[`TypeError`](../../typeerror) when invoked.

-   A property cannot be added, if the target object is not extensible.
-   A property cannot be added as or modified to be non-configurable, if
    it does not exists as a non-configurable own property of the target
    object.
-   A property may not be non-configurable, if a corresponding
    configurable property of the target object exists.
-   If a property has a corresponding target object property then
    `Object.defineProperty(target, prop, descriptor)` will not throw an
    exception.
-   In strict mode, a `false` return value from the `defineProperty()`
    handler will throw a [`TypeError`](../../typeerror) exception.



 
Examples
--------


 
### Trapping of defineProperty 

 
The following code traps
[`Object.defineProperty()`](../../object/defineproperty).

 
 
[js]


```js
const p = new Proxy(
  {},
  {
    defineProperty(target, prop, descriptor) {
      console.log(`called: ${prop}`);
      return true;
    },
  },
);

const desc = { configurable: true, enumerable: true, value: 10 };
Object.defineProperty(p, "a", desc); // "called: a"
```


When calling [`Object.defineProperty()`](../../object/defineproperty) or
[`Reflect.defineProperty()`](../../reflect/defineproperty), the
`descriptor` passed to `defineProperty()` trap has one
restriction---only following properties are usable (non-standard
properties will be ignored):

-   `enumerable`
-   `configurable`
-   `writable`
-   `value`
-   `get`
-   `set`

 
 
[js]


```js
const p = new Proxy(
  {},
  {
    defineProperty(target, prop, descriptor) {
      console.log(descriptor);
      return Reflect.defineProperty(target, prop, descriptor);
    },
  },
);

Object.defineProperty(p, "name", {
  value: "proxy",
  type: "custom",
}); // { value: 'proxy' }
```




Specifications
--------------

 
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-proxy-object-internal-methods-and-internal-slots-defineownproperty-p-desc]](https://tc39.es/ecma262/multipage/ordinary-and-exotic-objects-behaviours.html#sec-proxy-object-internal-methods-and-internal-slots-defineownproperty-p-desc)

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`defineProperty`

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
-   [`Object.defineProperty()`](../../object/defineproperty)
-   [`Reflect.defineProperty()`](../../reflect/defineproperty)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/defineProperty>

