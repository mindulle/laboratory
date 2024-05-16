Object.fromEntries()
====================

 
The `Object.fromEntries()` static method transforms a list of key-value
pairs into an object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Object.fromEntries(iterable)
```




 
### Parameters

 

[`iterable`](#iterable)

:   An [iterable](../../iteration_protocols#the_iterable_protocol), such
    as an [`Array`](../array) or [`Map`](../map), containing a list of
    objects. Each object should have two properties:

    [`0`](#0)

    :   A string or [symbol](../symbol) representing the property key.

    [`1`](#1)

    :   The property value.

    Typically, this object is implemented as a two-element array, with
    the first element being the property key and the second element
    being the property value.



 
### Return value 

 
A new object whose properties are given by the entries of the iterable.



 
Description
-----------

 
The `Object.fromEntries()` method takes a list of key-value pairs and
returns a new object whose properties are given by those entries. The
`iterable` argument is expected to be an object that implements an
`@@iterator` method. The method returns an iterator object that produces
two-element array-like objects. The first element is a value that will
be used as a property key, and the second element is the value to
associate with that property key.

`Object.fromEntries()` performs the reverse of
[`Object.entries()`](entries), except that `Object.entries()` only
returns string-keyed properties, while `Object.fromEntries()` can also
create symbol-keyed properties.

 
**Note:** Unlike [`Array.from()`](../array/from), `Object.fromEntries()`
does not use the value of `this`, so calling it on another constructor
does not create objects of that type.




 
Examples
--------


 
### Converting a Map to an Object 

 
With `Object.fromEntries`, you can convert from [`Map`](../map) to
[`Object`](../object):

 
 
[js]


```js
const map = new Map([
  ["foo", "bar"],
  ["baz", 42],
]);
const obj = Object.fromEntries(map);
console.log(obj); // { foo: "bar", baz: 42 }
```




 
### Converting an Array to an Object 

 
With `Object.fromEntries`, you can convert from [`Array`](../array) to
[`Object`](../object):

 
 
[js]


```js
const arr = [
  ["0", "a"],
  ["1", "b"],
  ["2", "c"],
];
const obj = Object.fromEntries(arr);
console.log(obj); // { 0: "a", 1: "b", 2: "c" }
```




 
### Object transformations 

 
With `Object.fromEntries`, its reverse method
[`Object.entries()`](entries), and [array manipulation
methods](../array#instance_methods), you are able to transform objects
like this:

 
 
[js]


```js
const object1 = { a: 1, b: 2, c: 3 };

const object2 = Object.fromEntries(
  Object.entries(object1).map(([key, val]) => [key, val * 2]),
);

console.log(object2);
// { a: 2, b: 4, c: 6 }
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.fromentries]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.fromentries)

  ---------------------------------------------------------------------------------------------------------------------


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

`fromEntries`

73

79

63

60

12.1

73

63

52

12.2

11.0

73

1.0

12.0.0

 
See also 
--------

 
-   [Polyfill of `Object.fromEntries` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-object)
-   [`Object.entries()`](entries)
-   [`Object.keys()`](keys)
-   [`Object.values()`](values)
-   [`Object.prototype.propertyIsEnumerable()`](propertyisenumerable)
-   [`Object.create()`](create)
-   [`Map.prototype.entries()`](../map/entries)
-   [`Map.prototype.keys()`](../map/keys)
-   [`Map.prototype.values()`](../map/values)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/fromEntries>

