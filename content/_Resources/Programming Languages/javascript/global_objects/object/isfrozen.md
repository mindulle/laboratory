Object.isFrozen()
=================

 
The `Object.isFrozen()` static method determines if an object is
[frozen](freeze).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Object.isFrozen(obj)
```




 
### Parameters

 

[`obj`](#obj)

:   The object which should be checked.



 
### Return value 

 
A [`Boolean`](../boolean) indicating whether or not the given object is
frozen.



 
Description
-----------

 
An object is frozen if and only if it is not [extensible](isextensible),
all its properties are non-configurable, and all its data properties
(that is, properties which are not accessor properties with getter or
setter components) are non-writable.



 
Examples
--------


 
### Using Object.isFrozen 

 
 
 
[js]


```js
// A new object is extensible, so it is not frozen.
Object.isFrozen({}); // false

// An empty object which is not extensible
// is vacuously frozen.
const vacuouslyFrozen = Object.preventExtensions({});
Object.isFrozen(vacuouslyFrozen); // true

// A new object with one property is also extensible,
// ergo not frozen.
const oneProp = { p: 42 };
Object.isFrozen(oneProp); // false

// Preventing extensions to the object still doesn't
// make it frozen, because the property is still
// configurable (and writable).
Object.preventExtensions(oneProp);
Object.isFrozen(oneProp); // false

// Deleting that property makes the object vacuously frozen.
delete oneProp.p;
Object.isFrozen(oneProp); // true

// A non-extensible object with a non-writable
// but still configurable property is not frozen.
const nonWritable = { e: "plep" };
Object.preventExtensions(nonWritable);
Object.defineProperty(nonWritable, "e", {
  writable: false,
}); // make non-writable
Object.isFrozen(nonWritable); // false

// Changing that property to non-configurable
// then makes the object frozen.
Object.defineProperty(nonWritable, "e", {
  configurable: false,
}); // make non-configurable
Object.isFrozen(nonWritable); // true

// A non-extensible object with a non-configurable
// but still writable property also isn't frozen.
const nonConfigurable = { release: "the kraken!" };
Object.preventExtensions(nonConfigurable);
Object.defineProperty(nonConfigurable, "release", {
  configurable: false,
});
Object.isFrozen(nonConfigurable); // false

// Changing that property to non-writable
// then makes the object frozen.
Object.defineProperty(nonConfigurable, "release", {
  writable: false,
});
Object.isFrozen(nonConfigurable); // true

// A non-extensible object with a configurable
// accessor property isn't frozen.
const accessor = {
  get food() {
    return "yum";
  },
};
Object.preventExtensions(accessor);
Object.isFrozen(accessor); // false

// When we make that property non-configurable it becomes frozen.
Object.defineProperty(accessor, "food", {
  configurable: false,
});
Object.isFrozen(accessor); // true

// But the easiest way for an object to be frozen
// is if Object.freeze has been called on it.
const frozen = { 1: 81 };
Object.isFrozen(frozen); // false
Object.freeze(frozen);
Object.isFrozen(frozen); // true

// By definition, a frozen object is non-extensible.
Object.isExtensible(frozen); // false

// Also by definition, a frozen object is sealed.
Object.isSealed(frozen); // true
```




 
### Non-object argument 

 
In ES5, if the argument to this method is not an object (a primitive),
then it will cause a [`TypeError`](../typeerror). In ES2015, it will
return `true` without any errors if a non-object argument is passed,
since primitives are, by definition, immutable.

 
 
[js]


```js
Object.isFrozen(1);
// TypeError: 1 is not an object (ES5 code)

Object.isFrozen(1);
// true                          (ES2015 code)
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.isfrozen]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.isfrozen)

  ---------------------------------------------------------------------------------------------------------------


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

`isFrozen`

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

 
-   [`Object.freeze()`](freeze)
-   [`Object.preventExtensions()`](preventextensions)
-   [`Object.isExtensible()`](isextensible)
-   [`Object.seal()`](seal)
-   [`Object.isSealed()`](issealed)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isFrozen>

