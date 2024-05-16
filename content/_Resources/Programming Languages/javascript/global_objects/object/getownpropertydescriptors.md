Object.getOwnPropertyDescriptors()
==================================

 
The `Object.getOwnPropertyDescriptors()` static method returns all own
property descriptors of a given object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Object.getOwnPropertyDescriptors(obj)
```




 
### Parameters

 

[`obj`](#obj)

:   The object for which to get all own property descriptors.



 
### Return value 

 
An object containing all own property descriptors of an object. Might be
an empty object, if there are no properties.



 
Description
-----------

 
This method permits examination of the precise description of all own
properties of an object. A *property* in JavaScript consists of either a
string-valued name or a [`Symbol`](../symbol) and a property descriptor.
Further information about property descriptor types and their attributes
can be found in [`Object.defineProperty()`](defineproperty).

A *property descriptor* is a record with some of the following
attributes:

[`value`](#value)

:   The value associated with the property (data descriptors only).

[`writable`](#writable)

:   `true` if and only if the value associated with the property may be
    changed (data descriptors only).

[`get`](#get)

:   A function which serves as a getter for the property, or
    [`undefined`](../undefined) if there is no getter (accessor
    descriptors only).

[`set`](#set)

:   A function which serves as a setter for the property, or
    [`undefined`](../undefined) if there is no setter (accessor
    descriptors only).

[`configurable`](#configurable)

:   `true` if and only if the type of this property descriptor may be
    changed and if the property may be deleted from the corresponding
    object.

[`enumerable`](#enumerable)

:   `true` if and only if this property shows up during enumeration of
    the properties on the corresponding object.



 
Examples
--------


 
### Creating a shallow copy 

 
Whereas the [`Object.assign()`](assign) method will only copy enumerable
and own properties from a source object to a target object, you are able
to use this method and [`Object.create()`](create) for a [shallow
copy](https://developer.mozilla.org/en-US/docs/Glossary/Shallow_copy)
between two unknown objects:

 
 
[js]


```js
Object.create(
  Object.getPrototypeOf(obj),
  Object.getOwnPropertyDescriptors(obj),
);
```




 
### Creating a subclass 

 
A typical way of creating a subclass is to define the subclass, set its
prototype to an instance of the superclass, and then define properties
on that instance. This can get awkward especially for getters and
setters. Instead, you can use this code to set the prototype:

 
 
[js]


```js
function superclass() {}
superclass.prototype = {
  // Define the superclass constructor, methods, and properties here
};
function subclass() {}
subclass.prototype = Object.create(superclass.prototype, {
  // Define the subclass constructor, methods, and properties here
});
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.getownpropertydescriptors]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.getownpropertydescriptors)

  -------------------------------------------------------------------------------------------------------------------------------------------------


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

`getOwnPropertyDescriptors`

54

15

50

41

10

54

50

41

10

6.0

54

1.0

7.0.0

 
See also 
--------

 
-   [Polyfill of `Object.getOwnPropertyDescriptors` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-object)
-   [`Object.getOwnPropertyDescriptor()`](getownpropertydescriptor)
-   [`Object.defineProperty()`](defineproperty)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptors>

