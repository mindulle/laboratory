Object.isExtensible()
=====================

 
The `Object.isExtensible()` static method determines if an object is
extensible (whether it can have new properties added to it).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Object.isExtensible(obj)
```




 
### Parameters

 

[`obj`](#obj)

:   The object which should be checked.



 
### Return value 

 
A [`Boolean`](../boolean) indicating whether or not the given object is
extensible.



 
Description
-----------

 
Objects are extensible by default: they can have new properties added to
them, and their `[[Prototype]]` can be re-assigned. An object can be
marked as non-extensible using one of
[`Object.preventExtensions()`](preventextensions),
[`Object.seal()`](seal), [`Object.freeze()`](freeze), or
[`Reflect.preventExtensions()`](../reflect/preventextensions).



 
Examples
--------


 
### Using Object.isExtensible 

 
 
 
[js]


```js
// New objects are extensible.
const empty = {};
Object.isExtensible(empty); // true

// They can be made un-extensible
Object.preventExtensions(empty);
Object.isExtensible(empty); // false

// Sealed objects are by definition non-extensible.
const sealed = Object.seal({});
Object.isExtensible(sealed); // false

// Frozen objects are also by definition non-extensible.
const frozen = Object.freeze({});
Object.isExtensible(frozen); // false
```




 
### Non-object argument 

 
In ES5, if the argument to this method is not an object (a primitive),
then it will cause a [`TypeError`](../typeerror). In ES2015, it will
return `false` without any errors if a non-object argument is passed,
since primitives are, by definition, immutable.

 
 
[js]


```js
Object.isExtensible(1);
// TypeError: 1 is not an object (ES5 code)

Object.isExtensible(1);
// false                         (ES2015 code)
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.isextensible]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.isextensible)

  -----------------------------------------------------------------------------------------------------------------------


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

6

12

4

12

5.1

18

4

12

5

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [`Object.preventExtensions()`](preventextensions)
-   [`Object.seal()`](seal)
-   [`Object.isSealed()`](issealed)
-   [`Object.freeze()`](freeze)
-   [`Object.isFrozen()`](isfrozen)
-   [`Reflect.isExtensible()`](../reflect/isextensible)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isExtensible>

