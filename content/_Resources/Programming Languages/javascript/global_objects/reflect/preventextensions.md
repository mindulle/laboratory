Reflect.preventExtensions()
===========================

 
The `Reflect.preventExtensions()` static method is like
[`Object.preventExtensions()`](../object/preventextensions). It prevents
new properties from ever being added to an object (i.e., prevents future
extensions to the object).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Reflect.preventExtensions(target)
```




 
### Parameters

 

[`target`](#target)

:   The target object on which to prevent extensions.



 
### Return value 

 
A [`Boolean`](../boolean) indicating whether or not the target was
successfully set to prevent extensions.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `target` is not an object.



 
Description
-----------

 
`Reflect.preventExtensions()` provides the reflective semantic of
preventing extensions of an object. The differences with
[`Object.preventExtensions()`](../object/preventextensions) are:

-   `Reflect.preventExtensions()` throws a [`TypeError`](../typeerror)
    if the target is not an object, while `Object.preventExtensions()`
    always returns non-object targets as-is.
-   `Reflect.preventExtensions()` returns a [`Boolean`](../boolean)
    indicating whether or not the target was successfully set to prevent
    extensions, while `Object.preventExtensions()` returns the target
    object.

`Reflect.preventExtensions()` invokes the `[[PreventExtensions]]`
[object internal method](../proxy#object_internal_methods) of `target`.



 
Examples
--------


 
### Using Reflect.preventExtensions() 

 
See also [`Object.preventExtensions()`](../object/preventextensions).

 
 
[js]


```js
// Objects are extensible by default.
const empty = {};
Reflect.isExtensible(empty); // true

// ...but that can be changed.
Reflect.preventExtensions(empty);
Reflect.isExtensible(empty); // false
```




 
### Difference with Object.preventExtensions() 

 
If the `target` argument to this method is not an object (a primitive),
then it will cause a [`TypeError`](../typeerror). With
[`Object.preventExtensions()`](../object/preventextensions), a
non-object `target` will be returned as-is without any errors.

 
 
[js]


```js
Reflect.preventExtensions(1);
// TypeError: 1 is not an object

Object.preventExtensions(1);
// 1
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-reflect.preventextensions]](https://tc39.es/ecma262/multipage/reflection.html#sec-reflect.preventextensions)

  --------------------------------------------------------------------------------------------------------------------------


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

 
-   [Polyfill of `Reflect.preventExtensions` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-reflect)
-   [`Reflect`](../reflect)
-   [`Object.preventExtensions()`](../object/preventextensions)
-   [`handler.preventExtensions()`](../proxy/proxy/preventextensions)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/preventExtensions>

