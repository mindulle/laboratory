Reflect.isExtensible()
======================

 
The `Reflect.isExtensible()` static method is like
[`Object.isExtensible()`](../object/isextensible). It determines if an
object is extensible (whether it can have new properties added to it).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Reflect.isExtensible(target)
```




 
### Parameters

 

[`target`](#target)

:   The target object which to check if it is extensible.



 
### Return value 

 
A [`Boolean`](../boolean) indicating whether or not the target is
extensible.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `target` is not an object.



 
Description
-----------

 
`Reflect.isExtensible()` provides the reflective semantic of checking if
an object is extensible. The only difference with
[`Object.isExtensible()`](../object/isextensible) is how non-object
targets are handled. `Reflect.isExtensible()` throws a
[`TypeError`](../typeerror) if the target is not an object, while
`Object.isExtensible()` always returns `false` for non-object targets.

`Reflect.isExtensible()` invokes the `[[IsExtensible]]` [object internal
method](../proxy#object_internal_methods) of `target`.



 
Examples
--------


 
### Using Reflect.isExtensible() 

 
See also [`Object.isExtensible()`](../object/isextensible).

 
 
[js]


```js
// New objects are extensible.
const empty = {};
Reflect.isExtensible(empty); // true

// ...but that can be changed.
Reflect.preventExtensions(empty);
Reflect.isExtensible(empty); // false

// Sealed objects are by definition non-extensible.
const sealed = Object.seal({});
Reflect.isExtensible(sealed); // false

// Frozen objects are also by definition non-extensible.
const frozen = Object.freeze({});
Reflect.isExtensible(frozen); // false
```




 
### Difference with Object.isExtensible() 

 
If the `target` argument to this method is not an object (a primitive),
then it will cause a [`TypeError`](../typeerror). With
[`Object.isExtensible()`](../object/isextensible), a non-object `target`
will return false without any errors.

 
 
[js]


```js
Reflect.isExtensible(1);
// TypeError: 1 is not an object

Object.isExtensible(1);
// false
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-reflect.isextensible]](https://tc39.es/ecma262/multipage/reflection.html#sec-reflect.isextensible)

  ----------------------------------------------------------------------------------------------------------------


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

 
-   [Polyfill of `Reflect.isExtensible` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-reflect)
-   [`Reflect`](../reflect)
-   [`Object.isExtensible()`](../object/isextensible)
-   [`handler.isExtensible()`](../proxy/proxy/isextensible)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/isExtensible>

