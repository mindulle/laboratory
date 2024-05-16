handler.deleteProperty()
========================

 
The `handler.deleteProperty()` method is a trap for the `[[Delete]]`
[object internal method](../../proxy#object_internal_methods), which is
used by operations such as the [`delete`](../../../operators/delete)
operator.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Proxy(target, {
  deleteProperty(target, property) {
  }
});
```




 
### Parameters

 
The following parameters are passed to the `deleteProperty()` method.
`this` is bound to the handler.

[`target`](#target)

:   The target object.

[`property`](#property)

:   The name or [`Symbol`](../../symbol) of the property to delete.



 
### Return value 

 
The `deleteProperty()` method must return a boolean value indicating
whether or not the property has been successfully deleted.



 
Description
-----------


 
### Interceptions

 
This trap can intercept these operations:

-   The [`delete`](../../../operators/delete) operator:
    `delete proxy[foo]` and `delete proxy.foo`
-   [`Reflect.deleteProperty()`](../../reflect/deleteproperty)

Or any other operation that invokes the `[[Delete]]` [internal
method](../../proxy#object_internal_methods).



 
### Invariants

 
If the following invariants are violated, the trap throws a
[`TypeError`](../../typeerror) when invoked.

-   A property cannot be deleted, if it exists as a non-configurable own
    property of the target object.



 
Examples
--------


 
### Trapping the delete operator 

 
The following code traps the [`delete`](../../../operators/delete)
operator.

 
 
[js]


```js
const p = new Proxy(
  {},
  {
    deleteProperty(target, prop) {
      if (!(prop in target)) {
        console.log(`property not found: ${prop}`);
        return false;
      }
      delete target[prop];
      console.log(`property removed: ${prop}`);
      return true;
    },
  },
);

p.a = 10;
console.log("a" in p); // true

const result1 = delete p.a; // "property removed: a"
console.log(result1); // true
console.log("a" in p); // false

const result2 = delete p.a; // "property not found: a"
console.log(result2); // false
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-proxy-object-internal-methods-and-internal-slots-delete-p]](https://tc39.es/ecma262/multipage/ordinary-and-exotic-objects-behaviours.html#sec-proxy-object-internal-methods-and-internal-slots-delete-p)

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`deleteProperty`

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
-   [`delete`](../../../operators/delete)
-   [`Reflect.deleteProperty()`](../../reflect/deleteproperty)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/deleteProperty>

