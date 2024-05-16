Reflect.deleteProperty()
========================

 
The `Reflect.deleteProperty()` static method is like the
[`delete`](../../operators/delete) operator, but as a function. It
deletes a property from an object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Reflect.deleteProperty(target, propertyKey)
```




 
### Parameters

 

[`target`](#target)

:   The target object on which to delete the property.

[`propertyKey`](#propertykey)

:   The name of the property to be deleted.



 
### Return value 

 
A boolean indicating whether or not the property was successfully
deleted.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `target` is not an object.



 
Description
-----------

 
`Reflect.deleteProperty()` provides the reflective semantic of the
[`delete`](../../operators/delete) operator. That is,
`Reflect.deleteProperty(target, propertyKey)` is semantically equivalent
to:

 
 
[js]


```js
delete target.propertyKey;
```


At the very low level, deleting a property returns a boolean (as is the
case with [the proxy handler](../proxy/proxy/deleteproperty)).
`Reflect.deleteProperty()` directly returns the status, while `delete`
would throw a [`TypeError`](../typeerror) in [strict
mode](../../strict_mode) if the status is `false`. In non-strict mode,
`delete` and `Reflect.deleteProperty()` have the same behavior.

`Reflect.deleteProperty()` invokes the `[[Delete]]` [object internal
method](../proxy#object_internal_methods) of `target`.



 
Examples
--------


 
### Using Reflect.deleteProperty() 

 
 
 
[js]


```js
const obj = { x: 1, y: 2 };
Reflect.deleteProperty(obj, "x"); // true
console.log(obj); // { y: 2 }

const arr = [1, 2, 3, 4, 5];
Reflect.deleteProperty(arr, "3"); // true
console.log(arr); // [1, 2, 3, undefined, 5]

// Returns true if no such property exists
Reflect.deleteProperty({}, "foo"); // true

// Returns false if a property is unconfigurable
Reflect.deleteProperty(Object.freeze({ foo: 1 }), "foo"); // false
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-reflect.deleteproperty]](https://tc39.es/ecma262/multipage/reflection.html#sec-reflect.deleteproperty)

  --------------------------------------------------------------------------------------------------------------------


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

 
-   [Polyfill of `Reflect.deleteProperty` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-reflect)
-   [`Reflect`](../reflect)
-   [`delete`](../../operators/delete)
-   [`handler.deleteProperty()`](../proxy/proxy/deleteproperty)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/deleteProperty>

