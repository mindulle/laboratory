Reflect.set()
=============

 
The `Reflect.set()` static method is like the [property
accessor](../../operators/property_accessors) and
[assignment](../../operators/assignment) syntax, but as a function.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Reflect.set(target, propertyKey, value)
Reflect.set(target, propertyKey, value, receiver)
```




 
### Parameters

 

[`target`](#target)

:   The target object on which to set the property.

[`propertyKey`](#propertykey)

:   The name of the property to set.

[`value`](#value)

:   The value to set.

[`receiver`](#receiver) [Optional]

:   The value of `this` provided for the call to the setter for
    `propertyKey` on `target`. If provided and `target` does not have a
    setter for `propertyKey`, the property will be set on `receiver`
    instead.



 
### Return value 

 
A [`Boolean`](../boolean) indicating whether or not setting the property
was successful.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `target` is not an object.



 
Description
-----------

 
`Reflect.set()` provides the reflective semantic of a [property
access](../../operators/property_accessors). That is,
`Reflect.set(target, propertyKey, value, receiver)` is semantically
equivalent to:

 
 
[js]


```js
target[propertyKey] = value;
```


Note that in a normal property access, `target` and `receiver` would
observably be the same object.

`Reflect.set()` invokes the `[[Set]]` [object internal
method](../proxy#object_internal_methods) of `target`.



 
Examples
--------


 
### Using Reflect.set() 

 
 
 
[js]


```js
// Object
const obj = {};
Reflect.set(obj, "prop", "value"); // true
obj.prop; // "value"

// Array
const arr = ["duck", "duck", "duck"];
Reflect.set(arr, 2, "goose"); // true
arr[2]; // "goose"

// It can truncate an array.
Reflect.set(arr, "length", 1); // true
arr; // ["duck"]

// With just one argument, propertyKey and value are "undefined".
Reflect.set(obj); // true
Reflect.getOwnPropertyDescriptor(obj, "undefined");
// { value: undefined, writable: true, enumerable: true, configurable: true }
```




 
### Different target and receiver 

 
When the `target` and `receiver` are different, `Reflect.set` will use
the property descriptor of `target` (to find the setter or determine if
the property is writable), but set the property on `receiver`.

 
 
[js]


```js
const target = {};
const receiver = {};
Reflect.set(target, "a", 2, receiver); // true
// target is {}; receiver is { a: 2 }

const target = { a: 1 };
const receiver = {};
Reflect.set(target, "a", 2, receiver); // true
// target is { a: 1 }; receiver is { a: 2 }

const target = {
  set a(v) {
    this.b = v;
  },
};
const receiver = {};
Reflect.set(target, "a", 2, receiver); // true
// target is { a: [Setter] }; receiver is { b: 2 }
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-reflect.set]](https://tc39.es/ecma262/multipage/reflection.html#sec-reflect.set)

  ----------------------------------------------------------------------------------------------


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

`set`

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

 
-   [Polyfill of `Reflect.set` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-reflect)
-   [`Reflect`](../reflect)
-   [Property accessors](../../operators/property_accessors)
-   [`handler.set()`](../proxy/proxy/set)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/set>

