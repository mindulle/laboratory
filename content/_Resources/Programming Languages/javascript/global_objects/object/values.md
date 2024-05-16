Object.values()
===============

 
The `Object.values()` static method returns an array of a given
object\'s own enumerable string-keyed property values.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Object.values(obj)
```




 
### Parameters

 

[`obj`](#obj)

:   An object.



 
### Return value 

 
An array containing the given object\'s own enumerable string-keyed
property values.



 
Description
-----------

 
`Object.values()` returns an array whose elements are values of
enumerable string-keyed properties found directly upon `object`. This is
the same as iterating with a [`for...in`](../../statements/for...in)
loop, except that a `for...in` loop enumerates properties in the
prototype chain as well. The order of the array returned by
`Object.values()` is the same as that provided by a
[`for...in`](../../statements/for...in) loop.

If you need the property keys, use [`Object.keys()`](keys) instead. If
you need both the property keys and values, use
[`Object.entries()`](entries) instead.



 
Examples
--------


 
### Using Object.values() 

 
 
 
[js]


```js
const obj = { foo: "bar", baz: 42 };
console.log(Object.values(obj)); // ['bar', 42]

// Array-like object
const arrayLikeObj1 = { 0: "a", 1: "b", 2: "c" };
console.log(Object.values(arrayLikeObj1)); // ['a', 'b', 'c']

// Array-like object with random key ordering
// When using numeric keys, the values are returned in the keys' numerical order
const arrayLikeObj2 = { 100: "a", 2: "b", 7: "c" };
console.log(Object.values(arrayLikeObj2)); // ['b', 'c', 'a']

// getFoo is a non-enumerable property
const myObj = Object.create(
  {},
  {
    getFoo: {
      value() {
        return this.foo;
      },
    },
  },
);
myObj.foo = "bar";
console.log(Object.values(myObj)); // ['bar']
```




 
### Using Object.values() on primitives 

 
Non-object arguments are [coerced to
objects](../object#object_coercion). [`undefined`](../undefined) and
[`null`](../../operators/null) cannot be coerced to objects and throw a
[`TypeError`](../typeerror) upfront. Only strings may have own
enumerable properties, while all other primitives return an empty array.

 
 
[js]


```js
// Strings have indices as enumerable own properties
console.log(Object.values("foo")); // ['f', 'o', 'o']

// Other primitives except undefined and null have no own properties
console.log(Object.values(100)); // []
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.values]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.values)

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

`values`

54

14

47

41

10.1

54

47

41

10.3

6.0

54

1.0

7.0.0

 
See also 
--------

 
-   [Polyfill of `Object.values` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-object)
-   [Enumerability and ownership of
    properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)
-   [`Object.keys()`](keys)
-   [`Object.entries()`](entries)
-   [`Object.prototype.propertyIsEnumerable()`](propertyisenumerable)
-   [`Object.create()`](create)
-   [`Object.getOwnPropertyNames()`](getownpropertynames)
-   [`Map.prototype.values()`](../map/values)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/values>

