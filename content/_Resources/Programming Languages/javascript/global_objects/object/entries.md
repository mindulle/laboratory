Object.entries()
================

 
The `Object.entries()` static method returns an array of a given
object\'s own enumerable string-keyed property key-value pairs.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Object.entries(obj)
```




 
### Parameters

 

[`obj`](#obj)

:   An object.



 
### Return value 

 
An array of the given object\'s own enumerable string-keyed property
key-value pairs. Each key-value pair is an array with two elements: the
first element is the property key (which is always a string), and the
second element is the property value.



 
Description
-----------

 
`Object.entries()` returns an array whose elements are arrays
corresponding to the enumerable string-keyed property key-value pairs
found directly upon `object`. This is the same as iterating with a
[`for...in`](../../statements/for...in) loop, except that a `for...in`
loop enumerates properties in the prototype chain as well. The order of
the array returned by `Object.entries()` is the same as that provided by
a [`for...in`](../../statements/for...in) loop.

If you only need the property keys, use [`Object.keys()`](keys) instead.
If you only need the property values, use [`Object.values()`](values)
instead.



 
Examples
--------


 
### Using Object.entries() 

 
 
 
[js]


```js
const obj = { foo: "bar", baz: 42 };
console.log(Object.entries(obj)); // [ ['foo', 'bar'], ['baz', 42] ]

const arrayLike = { 0: "a", 1: "b", 2: "c" };
console.log(Object.entries(arrayLike)); // [ ['0', 'a'], ['1', 'b'], ['2', 'c'] ]

const randomKeyOrder = { 100: "a", 2: "b", 7: "c" };
console.log(Object.entries(randomKeyOrder)); // [ ['2', 'b'], ['7', 'c'], ['100', 'a'] ]

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
console.log(Object.entries(myObj)); // [ ['foo', 'bar'] ]
```




 
### Using Object.entries() on primitives 

 
Non-object arguments are [coerced to
objects](../object#object_coercion). [`undefined`](../undefined) and
[`null`](../../operators/null) cannot be coerced to objects and throw a
[`TypeError`](../typeerror) upfront. Only strings may have own
enumerable properties, while all other primitives return an empty array.

 
 
[js]


```js
// Strings have indices as enumerable own properties
console.log(Object.entries("foo")); // [ ['0', 'f'], ['1', 'o'], ['2', 'o'] ]

// Other primitives except undefined and null have no own properties
console.log(Object.entries(100)); // []
```




 
### Converting an Object to a Map 

 
The [`Map()`](../map/map) constructor accepts an iterable of `entries`.
With `Object.entries`, you can easily convert from [`Object`](../object)
to [`Map`](../map):

 
 
[js]


```js
const obj = { foo: "bar", baz: 42 };
const map = new Map(Object.entries(obj));
console.log(map); // Map(2) {"foo" => "bar", "baz" => 42}
```




 
### Iterating through an Object 

 
Using [array
destructuring](../../operators/destructuring_assignment#array_destructuring),
you can iterate through objects easily.

 
 
[js]


```js
// Using for...of loop
const obj = { a: 5, b: 7, c: 9 };
for (const [key, value] of Object.entries(obj)) {
  console.log(`${key}${value}`); // "a 5", "b 7", "c 9"
}

// Using array methods
Object.entries(obj).forEach(([key, value]) => {
  console.log(`${key}${value}`); // "a 5", "b 7", "c 9"
});
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.entries]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.entries)

  -------------------------------------------------------------------------------------------------------------


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

`entries`

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

 
-   [Polyfill of `Object.entries` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-object)
-   [Enumerability and ownership of
    properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)
-   [`Object.keys()`](keys)
-   [`Object.values()`](values)
-   [`Object.prototype.propertyIsEnumerable()`](propertyisenumerable)
-   [`Object.create()`](create)
-   [`Object.fromEntries()`](fromentries)
-   [`Object.getOwnPropertyNames()`](getownpropertynames)
-   [`Map.prototype.entries()`](../map/entries)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/entries>

