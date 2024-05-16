Object.hasOwn()
===============

 
The `Object.hasOwn()` static method returns `true` if the specified
object has the indicated property as its *own* property. If the property
is inherited, or does not exist, the method returns `false`.

 
**Note:** `Object.hasOwn()` is intended as a replacement for
[`Object.prototype.hasOwnProperty()`](hasownproperty).



 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Object.hasOwn(obj, prop)
```




 
### Parameters

 

[`obj`](#obj)

:   The JavaScript object instance to test.

[`prop`](#prop)

:   The [`String`](../string) name or [Symbol](../symbol) of the
    property to test.



 
### Return value 

 
`true` if the specified object has directly defined the specified
property. Otherwise `false`



 
Description
-----------

 
The `Object.hasOwn()` method returns `true` if the specified property is
a direct property of the object --- even if the property value is `null`
or `undefined`. The method returns `false` if the property is inherited,
or has not been declared at all. Unlike the [`in`](../../operators/in)
operator, this method does not check for the specified property in the
object\'s prototype chain.

It is recommended over
[`Object.prototype.hasOwnProperty()`](hasownproperty) because it works
for [`null`-prototype objects](../object#null-prototype_objects) and
with objects that have overridden the inherited `hasOwnProperty()`
method. While it is possible to workaround these problems by calling
`Object.prototype.hasOwnProperty()` on an external object,
`Object.hasOwn()` is more intuitive.



 
Examples
--------


 
### Using hasOwn to test for a property\'s existence 

 
The following code shows how to determine whether the `example` object
contains a property named `prop`.

 
 
[js]


```js
const example = {};
Object.hasOwn(example, "prop"); // false - 'prop' has not been defined

example.prop = "exists";
Object.hasOwn(example, "prop"); // true - 'prop' has been defined

example.prop = null;
Object.hasOwn(example, "prop"); // true - own property exists with value of null

example.prop = undefined;
Object.hasOwn(example, "prop"); // true - own property exists with value of undefined
```




 
### Direct vs. inherited properties 

 
The following example differentiates between direct properties and
properties inherited through the prototype chain:

 
 
[js]


```js
const example = {};
example.prop = "exists";

// `hasOwn` will only return true for direct properties:
Object.hasOwn(example, "prop"); // true
Object.hasOwn(example, "toString"); // false
Object.hasOwn(example, "hasOwnProperty"); // false

// The `in` operator will return true for direct or inherited properties:
"prop" in example; // true
"toString" in example; // true
"hasOwnProperty" in example; // true
```




 
### Iterating over the properties of an object 

 
To iterate over the enumerable properties of an object, you *should*
use:

 
 
[js]


```js
const example = { foo: true, bar: true };
for (const name of Object.keys(example)) {
  // …
}
```


But if you need to use `for...in`, you can use `Object.hasOwn()` to skip
the inherited properties:

 
 
[js]


```js
const example = { foo: true, bar: true };
for (const name in example) {
  if (Object.hasOwn(example, name)) {
    // …
  }
}
```




 
### Checking if an Array index exists 

 
The elements of an [`Array`](../array) are defined as direct properties,
so you can use `hasOwn()` method to check whether a particular index
exists:

 
 
[js]


```js
const fruits = ["Apple", "Banana", "Watermelon", "Orange"];
Object.hasOwn(fruits, 3); // true ('Orange')
Object.hasOwn(fruits, 4); // false - not defined
```




 
### Problematic cases for hasOwnProperty 

 
This section demonstrates that `hasOwn()` is immune to the problems that
affect `hasOwnProperty`. Firstly, it can be used with objects that have
reimplemented `hasOwnProperty()`:

 
 
[js]


```js
const foo = {
  hasOwnProperty() {
    return false;
  },
  bar: "The dragons be out of office",
};

if (Object.hasOwn(foo, "bar")) {
  console.log(foo.bar); // true - re-implementation of hasOwnProperty() does not affect Object
}
```


It can also be used with [`null`-prototype
objects](../object#null-prototype_objects). These do not inherit from
`Object.prototype`, and so `hasOwnProperty()` is inaccessible.

 
 
[js]


```js
const foo = Object.create(null);
foo.prop = "exists";
if (Object.hasOwn(foo, "prop")) {
  console.log(foo.prop); // true - works irrespective of how the object is created.
}
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.hasown]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.hasown)

  -----------------------------------------------------------------------------------------------------------


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

`hasOwn`

93

93

92

79

15.4

93

92

66

15.4

17.0

93

1.13

16.9.0

 
See also 
--------

 
-   [Polyfill of `Object.hasOwn` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-object)
-   [`Object.prototype.hasOwnProperty()`](hasownproperty)
-   [Enumerability and ownership of
    properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)
-   [`Object.getOwnPropertyNames()`](getownpropertynames)
-   [`for...in`](../../statements/for...in)
-   [`in`](../../operators/in)
-   [Inheritance and the prototype
    chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwn>

