Object.getOwnPropertyNames()
============================

 
The `Object.getOwnPropertyNames()` static method returns an array of all
properties (including non-enumerable properties except for those which
use Symbol) found directly in a given object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Object.getOwnPropertyNames(obj)
```




 
### Parameters

 

[`obj`](#obj)

:   The object whose enumerable and non-enumerable properties are to be
    returned.



 
### Return value 

 
An array of strings that corresponds to the properties found directly in
the given object.



 
Description
-----------

 
`Object.getOwnPropertyNames()` returns an array whose elements are
strings corresponding to the enumerable and non-enumerable properties
found directly in a given object `obj`. The ordering of the enumerable
properties in the array is consistent with the ordering exposed by a
[`for...in`](../../statements/for...in) loop (or by
[`Object.keys()`](keys)) over the properties of the object. The
non-negative integer keys of the object (both enumerable and
non-enumerable) are added in ascending order to the array first,
followed by the string keys in the order of insertion.

In ES5, if the argument to this method is not an object (a primitive),
then it will cause a [`TypeError`](../typeerror). In ES2015, a
non-object argument will be coerced to an object.

 
 
[js]


```js
Object.getOwnPropertyNames("foo");
// TypeError: "foo" is not an object (ES5 code)

Object.getOwnPropertyNames("foo");
// ["0", "1", "2", "length"]  (ES2015 code)
```




 
Examples
--------


 
### Using Object.getOwnPropertyNames() 

 
 
 
[js]


```js
const arr = ["a", "b", "c"];
console.log(Object.getOwnPropertyNames(arr).sort());
// ["0", "1", "2", "length"]

// Array-like object
const obj = { 0: "a", 1: "b", 2: "c" };
console.log(Object.getOwnPropertyNames(obj).sort());
// ["0", "1", "2"]

Object.getOwnPropertyNames(obj).forEach((val, idx, array) => {
  console.log(`${val} -> ${obj[val]}`);
});
// 0 -> a
// 1 -> b
// 2 -> c

// non-enumerable property
const myObj = Object.create(
  {},
  {
    getFoo: {
      value() {
        return this.foo;
      },
      enumerable: false,
    },
  },
);
myObj.foo = 1;

console.log(Object.getOwnPropertyNames(myObj).sort()); // ["foo", "getFoo"]
```


If you want only the enumerable properties, see [`Object.keys()`](keys)
or use a [`for...in`](../../statements/for...in) loop (note that this
will also return enumerable properties found along the prototype chain
for the object unless the latter is filtered with
[`Object.hasOwn()`](hasown)).

Items on the prototype chain are not listed:

 
 
[js]


```js
function ParentClass() {}
ParentClass.prototype.inheritedMethod = function () {};

function ChildClass() {
  this.prop = 5;
  this.method = function () {};
}
ChildClass.prototype = new ParentClass();
ChildClass.prototype.prototypeMethod = function () {};

console.log(Object.getOwnPropertyNames(new ChildClass()));
// ["prop", "method"]
```




 
### Get non-enumerable properties only 

 
This uses the [`Array.prototype.filter()`](../array/filter) function to
remove the enumerable keys (obtained with [`Object.keys()`](keys)) from
a list of all keys (obtained with `Object.getOwnPropertyNames()`) thus
giving only the non-enumerable keys as output.

 
 
[js]


```js
const target = myObject;
const enumAndNonenum = Object.getOwnPropertyNames(target);
const enumOnly = new Set(Object.keys(target));
const nonenumOnly = enumAndNonenum.filter((key) => !enumOnly.has(key));

console.log(nonenumOnly);
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.getownpropertynames]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.getownpropertynames)

  -------------------------------------------------------------------------------------------------------------------------------------


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

`getOwnPropertyNames`

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

 
-   [Polyfill of `Object.getOwnPropertyNames` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-object)
-   [Enumerability and ownership of
    properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)
-   [`Object.hasOwn()`](hasown)
-   [`Object.prototype.propertyIsEnumerable()`](propertyisenumerable)
-   [`Object.create()`](create)
-   [`Object.keys()`](keys)
-   [`Array.prototype.forEach()`](../array/foreach)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyNames>

