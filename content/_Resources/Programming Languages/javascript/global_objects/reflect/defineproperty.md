Reflect.defineProperty()
========================

 
The `Reflect.defineProperty()` static method is like
[`Object.defineProperty()`](../object/defineproperty) but returns a
[`Boolean`](../boolean).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Reflect.defineProperty(target, propertyKey, attributes)
```




 
### Parameters

 

[`target`](#target)

:   The target object on which to define the property.

[`propertyKey`](#propertykey)

:   The name of the property to be defined or modified.

[`attributes`](#attributes)

:   The attributes for the property being defined or modified.



 
### Return value 

 
A boolean indicating whether or not the property was successfully
defined.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `target` or `attributes` is not an object.



 
Description
-----------

 
`Reflect.defineProperty()` provides the reflective semantic of defining
an own property on an object. At the very low level, defining a property
returns a boolean (as is the case with [the proxy
handler](../proxy/proxy/defineproperty)).
[`Object.defineProperty()`](../object/defineproperty) provides nearly
the same semantic, but it throws a [`TypeError`](../typeerror) if the
status is `false` (the operation was unsuccessful), while
`Reflect.defineProperty()` directly returns the status.

Many built-in operations would also define own properties on objects.
The most significant difference between defining properties and
[setting](set) them is that [setters](../../functions/set) aren\'t
invoked. For example, [class fields](publicClassFields.md)
directly define properties on the instance without invoking setters.

 
 
[js]


```js
class B extends class A {
  set a(v) {
    console.log("Setter called");
  }
} {
  a = 1; // Nothing logged
}
```


`Reflect.defineProperty()` invokes the `[[DefineOwnProperty]]` [object
internal method](../proxy#object_internal_methods) of `target`.



 
Examples
--------


 
### Using Reflect.defineProperty() 

 
 
 
[js]


```js
const obj = {};
Reflect.defineProperty(obj, "x", { value: 7 }); // true
console.log(obj.x); // 7
```




 
### Checking if property definition has been successful 

 
With [`Object.defineProperty()`](../object/defineproperty), which
returns an object if successful, or throws a [`TypeError`](../typeerror)
otherwise, you would use a [`try...catch`](../../statements/try...catch)
block to catch any error that occurred while defining a property.

Because `Reflect.defineProperty()` returns a Boolean success status, you
can just use an [`if...else`](../../statements/if...else) block here:

 
 
[js]


```js
if (Reflect.defineProperty(target, property, attributes)) {
  // success
} else {
  // failure
}
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-reflect.defineproperty]](https://tc39.es/ecma262/multipage/reflection.html#sec-reflect.defineproperty)

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

`defineProperty`

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

 
-   [Polyfill of `Reflect.defineProperty` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-reflect)
-   [`Reflect`](../reflect)
-   [`Object.defineProperty()`](../object/defineproperty)
-   [`handler.defineProperty()`](../proxy/proxy/defineproperty)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/defineProperty>

