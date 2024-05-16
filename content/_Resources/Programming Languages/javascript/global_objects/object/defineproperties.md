Object.defineProperties()
=========================

 
The `Object.defineProperties()` static method defines new or modifies
existing properties directly on an object, returning the object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Object.defineProperties(obj, props)
```




 
### Parameters

 

[`obj`](#obj)

:   The object on which to define or modify properties.

[`props`](#props)

:   An object whose keys represent the names of properties to be defined
    or modified and whose values are objects describing those
    properties. Each value in `props` must be either a data descriptor
    or an accessor descriptor; it cannot be both (see
    [`Object.defineProperty()`](defineproperty) for more details).

    Data descriptors and accessor descriptors may optionally contain the
    following keys:

    [`configurable`](#configurable)

    :   `true` if and only if the type of this property descriptor may
        be changed and if the property may be deleted from the
        corresponding object. `false`

    [`enumerable`](#enumerable)

    :   `true` if and only if this property shows up during enumeration
        of the properties on the corresponding object. `false`

    A data descriptor also has the following optional keys:

    [`value`](#value)

    :   The value associated with the property. Can be any valid
        JavaScript value (number, object, function, etc.). **Defaults to
        [`undefined`](../undefined).**

    [`writable`](#writable)

    :   `true` if and only if the value associated with the property may
        be changed with an [assignment
        operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#assignment_operators).
        `false`

    An accessor descriptor also has the following optional keys:

    [`get`](#get)

    :   A function which serves as a getter for the property, or
        [`undefined`](../undefined) if there is no getter. The
        function\'s return value will be used as the value of the
        property. **Defaults to [`undefined`](../undefined).**

    [`set`](#set)

    :   A function which serves as a setter for the property, or
        [`undefined`](../undefined) if there is no setter. The function
        will receive as its only argument the new value being assigned
        to the property. **Defaults to [`undefined`](../undefined).**

    If a descriptor has neither of `value`, `writable`, `get` and `set`
    keys, it is treated as a data descriptor. If a descriptor has both
    `value` or `writable` and `get` or `set` keys, an exception is
    thrown.



 
### Return value 

 
The object that was passed to the function.



 
Examples
--------


 
### Using Object.defineProperties 

 
 
 
[js]


```js
const obj = {};
Object.defineProperties(obj, {
  property1: {
    value: true,
    writable: true,
  },
  property2: {
    value: "Hello",
    writable: false,
  },
  // etc. etc.
});
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.defineproperties]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.defineproperties)

  -------------------------------------------------------------------------------------------------------------------------------


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

`defineProperties`

5

12

4

11.6

5

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

 
-   [Polyfill of `Object.defineProperties` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-object)
-   [`Object.defineProperty()`](defineproperty)
-   [`Object.keys()`](keys)
-   [Enumerability and ownership of
    properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperties>

