Object.keys()
=============

 
The `Object.keys()` static method returns an array of a given object\'s
own enumerable string-keyed property names.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Object.keys(obj)
```




 
### Parameters

 

[`obj`](#obj)

:   An object.



 
### Return value 

 
An array of strings representing the given object\'s own enumerable
string-keyed property keys.



 
Description
-----------

 
`Object.keys()` returns an array whose elements are strings
corresponding to the enumerable string-keyed property names found
directly upon `object`. This is the same as iterating with a
[`for...in`](../../statements/for...in) loop, except that a `for...in`
loop enumerates properties in the prototype chain as well. The order of
the array returned by `Object.keys()` is the same as that provided by a
[`for...in`](../../statements/for...in) loop.

If you need the property values, use [`Object.values()`](values)
instead. If you need both the property keys and values, use
[`Object.entries()`](entries) instead.



 
Examples
--------


 
### Using Object.keys() 

 
 
 
[js]


```js
// Simple array
const arr = ["a", "b", "c"];
console.log(Object.keys(arr)); // ['0', '1', '2']

// Array-like object
const obj = { 0: "a", 1: "b", 2: "c" };
console.log(Object.keys(obj)); // ['0', '1', '2']

// Array-like object with random key ordering
const anObj = { 100: "a", 2: "b", 7: "c" };
console.log(Object.keys(anObj)); // ['2', '7', '100']

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
myObj.foo = 1;
console.log(Object.keys(myObj)); // ['foo']
```


If you want *all* string-keyed own properties, including non-enumerable
ones, see [`Object.getOwnPropertyNames()`](getownpropertynames).



 
### Using Object.keys() on primitives 

 
Non-object arguments are [coerced to
objects](../object#object_coercion). [`undefined`](../undefined) and
[`null`](../../operators/null) cannot be coerced to objects and throw a
[`TypeError`](../typeerror) upfront. Only strings may have own
enumerable properties, while all other primitives return an empty array.

 
 
[js]


```js
// Strings have indices as enumerable own properties
console.log(Object.keys("foo")); // ['0', '1', '2']

// Other primitives except undefined and null have no own properties
console.log(Object.keys(100)); // []
```


 
**Note:** In ES5, passing a non-object to `Object.keys()` threw a
[`TypeError`](../typeerror).




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.keys]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.keys)

  -------------------------------------------------------------------------------------------------------


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

`keys`

5

12

4

12

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

 
-   [Polyfill of `Object.keys` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-object)
-   [Enumerability and ownership of
    properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)
-   [`Object.entries()`](entries)
-   [`Object.values()`](values)
-   [`Object.prototype.propertyIsEnumerable()`](propertyisenumerable)
-   [`Object.create()`](create)
-   [`Object.getOwnPropertyNames()`](getownpropertynames)
-   [`Map.prototype.keys()`](../map/keys)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys>

