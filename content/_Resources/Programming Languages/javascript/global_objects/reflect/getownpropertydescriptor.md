Reflect.getOwnPropertyDescriptor()
==================================

 
The `Reflect.getOwnPropertyDescriptor()` static method is like
[`Object.getOwnPropertyDescriptor()`](../object/getownpropertydescriptor).
It returns a property descriptor of the given property if it exists on
the object, [`undefined`](../undefined) otherwise.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Reflect.getOwnPropertyDescriptor(target, propertyKey)
```




 
### Parameters

 

[`target`](#target)

:   The target object in which to look for the property.

[`propertyKey`](#propertykey)

:   The name of the property to get an own property descriptor for.



 
### Return value 

 
A property descriptor object if the property exists as an own property
of `target`; otherwise, [`undefined`](../undefined).



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `target` is not an object.



 
Description
-----------

 
`Reflect.getOwnPropertyDescriptor()` provides the reflective semantic of
retrieving the property descriptor of an object. The only difference
with
[`Object.getOwnPropertyDescriptor()`](../object/getownpropertydescriptor)
is how non-object targets are handled.
`Reflect.getOwnPropertyDescriptor()` throws a
[`TypeError`](../typeerror) if the target is not an object, while
`Object.getOwnPropertyDescriptor()` coerces it to an object.

`Reflect.getOwnPropertyDescriptor()` invokes the `[[GetOwnProperty]]`
[object internal method](../proxy#object_internal_methods) of `target`.



 
Examples
--------


 
### Using Reflect.getOwnPropertyDescriptor() 

 
 
 
[js]


```js
Reflect.getOwnPropertyDescriptor({ x: "hello" }, "x");
// {value: "hello", writable: true, enumerable: true, configurable: true}

Reflect.getOwnPropertyDescriptor({ x: "hello" }, "y");
// undefined

Reflect.getOwnPropertyDescriptor([], "length");
// {value: 0, writable: true, enumerable: false, configurable: false}
```




 
### Difference with Object.getOwnPropertyDescriptor() 

 
If the `target` argument to this method is not an object (a primitive),
then it will cause a [`TypeError`](../typeerror). With
[`Object.getOwnPropertyDescriptor`](../object/getownpropertydescriptor),
a non-object first argument will be coerced to an object at first.

 
 
[js]


```js
Reflect.getOwnPropertyDescriptor("foo", 0);
// TypeError: "foo" is not non-null object

Object.getOwnPropertyDescriptor("foo", 0);
// { value: "f", writable: false, enumerable: true, configurable: false }
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-reflect.getownpropertydescriptor]](https://tc39.es/ecma262/multipage/reflection.html#sec-reflect.getownpropertydescriptor)

  ----------------------------------------------------------------------------------------------------------------------------------------


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

 
-   [Polyfill of `Reflect.getOwnPropertyDescriptor` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-reflect)
-   [`Reflect`](../reflect)
-   [`Object.getOwnPropertyDescriptor()`](../object/getownpropertydescriptor)
-   [`handler.getOwnPropertyDescriptor()`](../proxy/proxy/getownpropertydescriptor)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/getOwnPropertyDescriptor>

