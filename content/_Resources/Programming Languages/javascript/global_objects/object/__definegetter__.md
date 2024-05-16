Object.prototype.\_\_defineGetter\_\_()
=======================================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


 
**Note:** This feature is deprecated in favor of defining
[getters](../../functions/get) using the [object initializer
syntax](../../operators/object_initializer) or the
[`Object.defineProperty()`](defineproperty) API. This method\'s behavior
is only specified for web compatibility, and is not required to be
implemented in any platform. It may not work everywhere.


The `__defineGetter__()` method of [`Object`](../object) instances binds
an object\'s property to a function to be called when that property is
looked up.


 
Syntax
------

 
 
 
[js]


```js
__defineGetter__(prop, func)
```




 
### Parameters

 

[`prop`](#prop)

:   A string containing the name of the property that the getter `func`
    is bound to.

[`func`](#func)

:   A function to be bound to a lookup of the specified property.



 
### Return value 

 
None ([`undefined`](../undefined)).



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `func` is not a function.



 
Description
-----------

 
All objects that inherit from `Object.prototype` (that is, all except
[`null`-prototype objects](../object#null-prototype_objects)) inherit
the `__defineGetter__()` method. This method allows a
[getter](../../functions/get) to be defined on a pre-existing object.
This is equivalent to
[`Object.defineProperty(obj, prop, { get: func, configurable: true, enumerable: true })`](defineproperty),
which means the property is enumerable and configurable, and any
existing setter, if present, is preserved.

`__defineGetter__()` is defined in the spec as \"normative optional\",
which means no implementation is required to implement this. However,
all major browsers implement it, and due to its continued usage, it\'s
unlikely to be removed. If a browser implements `__defineGetter__()`, it
also needs to implement the [`__lookupGetter__()`](__lookupgetter__),
[`__lookupSetter__()`](__lookupsetter__), and
[`__defineSetter__()`](__definesetter__) methods.



 
Examples
--------


 
### Using \_\_defineGetter\_\_() 

 
 
 
[js]


```js
const o = {};
o.__defineGetter__("gimmeFive", function () {
  return 5;
});
console.log(o.gimmeFive); // 5
```




 
### Defining a getter property in standard ways 

 
You can use the `get` syntax to define a getter when the object is first
initialized.

 
 
[js]


```js
const o = {
  get gimmeFive() {
    return 5;
  },
};
console.log(o.gimmeFive); // 5
```


You may also use [`Object.defineProperty()`](defineproperty) to define a
getter on an object after it\'s been created. Compared to
`__defineGetter__()`, this method allows you to control the getter\'s
enumerability and configurability, as well as defining
[symbol](../symbol) properties. The `Object.defineProperty()` method
also works with [`null`-prototype
objects](../object#null-prototype_objects), which don\'t inherit from
`Object.prototype` and therefore don\'t have the `__defineGetter__()`
method.

 
 
[js]


```js
const o = {};
Object.defineProperty(o, "gimmeFive", {
  get() {
    return 5;
  },
  configurable: true,
  enumerable: true,
});
console.log(o.gimmeFive); // 5
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.prototype.\_\_defineGetter\_\_]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#sec-object.prototype.__defineGetter__)

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

`__defineGetter__`

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

 
-   [Polyfill of `Object.prototype.__defineGetter__` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-object)
-   [`Object.prototype.__defineSetter__()`](__definesetter__)
-   [`get`](../../functions/get)
-   [`Object.defineProperty()`](defineproperty)
-   [`Object.prototype.__lookupGetter__()`](__lookupgetter__)
-   [`Object.prototype.__lookupSetter__()`](__lookupsetter__)
-   [JS Guide: Defining Getters and
    Setters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_objects#defining_getters_and_setters)
-   [Firefox bug 647423](https://bugzil.la/647423)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/__defineGetter__>

