Object.prototype.\_\_defineSetter\_\_()
=======================================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


 
**Note:** This feature is deprecated in favor of defining
[setters](../../functions/set) using the [object initializer
syntax](../../operators/object_initializer) or the
[`Object.defineProperty()`](defineproperty) API. This method\'s behavior
is only specified for web compatibility, and is not required to be
implemented in any platform. It may not work everywhere.


The `__defineSetter__()` method of [`Object`](../object) instances binds
an object\'s property to a function to be called when an attempt is made
to set that property.


 
Syntax
------

 
 
 
[js]


```js
__defineSetter__(prop, func)
```




 
### Parameters

 

[`prop`](#prop)

:   A string containing the name of the property that the setter `func`
    is bound to.

[`func`](#func)

:   A function to be called when there is an attempt to set the
    specified property. This function receives the following parameter:

    [`val`](#val)

    :   The value attempted to be assigned to `prop`.



 
### Return value 

 
None ([`undefined`](../undefined)).



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `func` is not a function.



 
Description
-----------

 
All objects that inherit from `Object.prototype` (that is, all except
[`null`-prototype objects](../object#null-prototype_objects)) inherit
the `__defineSetter__()` method. This method allows a
[setter](../../functions/set) to be defined on a pre-existing object.
This is equivalent to
[`Object.defineProperty(obj, prop, { set: func, configurable: true, enumerable: true })`](defineproperty),
which means the property is enumerable and configurable, and any
existing getter, if present, is preserved.

`__defineSetter__()` is defined in the spec as \"normative optional\",
which means no implementation is required to implement this. However,
all major browsers implement it, and due to its continued usage, it\'s
unlikely to be removed. If a browser implements `__defineSetter__()`, it
also needs to implement the [`__lookupGetter__()`](__lookupgetter__),
[`__lookupSetter__()`](__lookupsetter__), and
[`__defineGetter__()`](__definegetter__) methods.



 
Examples
--------


 
### Using \_\_defineSetter\_\_() 

 
 
 
[js]


```js
const o = {};
o.__defineSetter__("value", function (val) {
  this.anotherValue = val;
});
o.value = 5;
console.log(o.value); // undefined
console.log(o.anotherValue); // 5
```




 
### Defining a setter property in standard ways 

 
You can use the `set` syntax to define a setter when the object is first
initialized.

 
 
[js]


```js
const o = {
  set value(val) {
    this.anotherValue = val;
  },
};
o.value = 5;
console.log(o.value); // undefined
console.log(o.anotherValue); // 5
```


You may also use [`Object.defineProperty()`](defineproperty) to define a
setter on an object after it\'s been created. Compared to
`__defineSetter__()`, this method allows you to control the setter\'s
enumerability and configurability, as well as defining
[symbol](../symbol) properties. The `Object.defineProperty()` method
also works with [`null`-prototype
objects](../object#null-prototype_objects), which don\'t inherit from
`Object.prototype` and therefore don\'t have the `__defineSetter__()`
method.

 
 
[js]


```js
const o = {};
Object.defineProperty(o, "value", {
  set(val) {
    this.anotherValue = val;
  },
  configurable: true,
  enumerable: true,
});
o.value = 5;
console.log(o.value); // undefined
console.log(o.anotherValue); // 5
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.prototype.\_\_defineSetter\_\_]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#sec-object.prototype.__defineSetter__)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`__defineSetter__`

1

12

1Starting with Firefox 48, this method can no longer be called at the
global scope without any object. A `TypeError` will be thrown otherwise.
Previously, the global object was used in these cases automatically, but
this is no longer the case.

9.5

3

18

4

10.1

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [Polyfill of `Object.prototype.__defineSetter__` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-object)
-   [`Object.prototype.__defineGetter__()`](__definegetter__)
-   [`set`](../../functions/set)
-   [`Object.defineProperty()`](defineproperty)
-   [`Object.prototype.__lookupGetter__()`](__lookupgetter__)
-   [`Object.prototype.__lookupSetter__()`](__lookupsetter__)
-   [JS Guide: Defining Getters and
    Setters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_objects#defining_getters_and_setters)
-   [Firefox bug 647423](https://bugzil.la/647423)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/__defineSetter__>

