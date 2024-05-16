Object.assign()
===============

 
The `Object.assign()` static method copies all
[enumerable](propertyisenumerable) [own properties](hasown) from one or
more *source objects* to a *target object*. It returns the modified
target object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Object.assign(target)
Object.assign(target, source1)
Object.assign(target, source1, source2)
Object.assign(target, source1, source2, /* …, */ sourceN)
```




 
### Parameters

 

[`target`](#target)

:   The target object --- what to apply the sources\' properties to,
    which is returned after it is modified.

[`source1`](#source1), ..., `sourceN`

:   The source object(s) --- objects containing the properties you want
    to apply.



 
### Return value 

 
The target object.



 
Description
-----------

 
Properties in the target object are overwritten by properties in the
sources if they have the same [key](keys). Later sources\' properties
overwrite earlier ones.

The `Object.assign()` method only copies *enumerable* and *own*
properties from a source object to a target object. It uses `[[Get]]` on
the source and `[[Set]]` on the target, so it will invoke
[getters](../../functions/get) and [setters](../../functions/set).
Therefore it *assigns* properties, versus copying or defining new
properties. This may make it unsuitable for merging new properties into
a prototype if the merge sources contain getters.

For copying property definitions (including their enumerability) into
prototypes, use
[`Object.getOwnPropertyDescriptor()`](getownpropertydescriptor) and
[`Object.defineProperty()`](defineproperty) instead.

Both [`String`](../string) and [`Symbol`](../symbol) properties are
copied.

In case of an error, for example if a property is non-writable, a
[`TypeError`](../typeerror) is raised, and the `target` object is
changed if any properties are added before the error is raised.

 
**Note:** `Object.assign()` does not throw on
[`null`](../../operators/null) or [`undefined`](../undefined) sources.




 
Examples
--------


 
### Cloning an object 

 
 
 
[js]


```js
const obj = { a: 1 };
const copy = Object.assign({}, obj);
console.log(copy); // { a: 1 }
```




 
### Warning for Deep Clone 

 
For [deep
cloning](https://developer.mozilla.org/en-US/docs/Glossary/Deep_copy),
we need to use alternatives like
[`structuredClone()`](https://developer.mozilla.org/en-US/docs/Web/API/structuredClone),
because `Object.assign()` copies property values.

If the source value is a reference to an object, it only copies the
reference value.

 
 
[js]


```js
const obj1 = { a: 0, b: { c: 0 } };
const obj2 = Object.assign({}, obj1);
console.log(obj2); // { a: 0, b: { c: 0 } }

obj1.a = 1;
console.log(obj1); // { a: 1, b: { c: 0 } }
console.log(obj2); // { a: 0, b: { c: 0 } }

obj2.a = 2;
console.log(obj1); // { a: 1, b: { c: 0 } }
console.log(obj2); // { a: 2, b: { c: 0 } }

obj2.b.c = 3;
console.log(obj1); // { a: 1, b: { c: 3 } }
console.log(obj2); // { a: 2, b: { c: 3 } }

// Deep Clone
const obj3 = { a: 0, b: { c: 0 } };
const obj4 = structuredClone(obj3);
obj3.a = 4;
obj3.b.c = 4;
console.log(obj4); // { a: 0, b: { c: 0 } }
```




 
### Merging objects 

 
 
 
[js]


```js
const o1 = { a: 1 };
const o2 = { b: 2 };
const o3 = { c: 3 };

const obj = Object.assign(o1, o2, o3);
console.log(obj); // { a: 1, b: 2, c: 3 }
console.log(o1); // { a: 1, b: 2, c: 3 }, target object itself is changed.
```




 
### Merging objects with same properties 

 
 
 
[js]


```js
const o1 = { a: 1, b: 1, c: 1 };
const o2 = { b: 2, c: 2 };
const o3 = { c: 3 };

const obj = Object.assign({}, o1, o2, o3);
console.log(obj); // { a: 1, b: 2, c: 3 }
```


The properties are overwritten by other objects that have the same
properties later in the parameters order.



 
### Copying symbol-typed properties 

 
 
 
[js]


```js
const o1 = { a: 1 };
const o2 = { [Symbol("foo")]: 2 };

const obj = Object.assign({}, o1, o2);
console.log(obj); // { a : 1, [Symbol("foo")]: 2 } (cf. bug 1207182 on Firefox)
Object.getOwnPropertySymbols(obj); // [Symbol(foo)]
```




 
### Properties on the prototype chain and non-enumerable properties cannot be copied 

 
 
 
[js]


```js
const obj = Object.create(
  // foo is on obj's prototype chain.
  { foo: 1 },
  {
    bar: {
      value: 2, // bar is a non-enumerable property.
    },
    baz: {
      value: 3,
      enumerable: true, // baz is an own enumerable property.
    },
  },
);

const copy = Object.assign({}, obj);
console.log(copy); // { baz: 3 }
```




 
### Primitives will be wrapped to objects 

 
 
 
[js]


```js
const v1 = "abc";
const v2 = true;
const v3 = 10;
const v4 = Symbol("foo");

const obj = Object.assign({}, v1, null, v2, undefined, v3, v4);
// Primitives will be wrapped, null and undefined will be ignored.
// Note, only string wrappers can have own enumerable properties.
console.log(obj); // { "0": "a", "1": "b", "2": "c" }
```




 
### Exceptions will interrupt the ongoing copying task 

 
 
 
[js]


```js
const target = Object.defineProperty({}, "foo", {
  value: 1,
  writable: false,
}); // target.foo is a read-only property

Object.assign(target, { bar: 2 }, { foo2: 3, foo: 3, foo3: 3 }, { baz: 4 });
// TypeError: "foo" is read-only
// The Exception is thrown when assigning target.foo

console.log(target.bar); // 2, the first source was copied successfully.
console.log(target.foo2); // 3, the first property of the second source was copied successfully.
console.log(target.foo); // 1, exception is thrown here.
console.log(target.foo3); // undefined, assign method has finished, foo3 will not be copied.
console.log(target.baz); // undefined, the third source will not be copied either.
```




 
### Copying accessors 

 
 
 
[js]


```js
const obj = {
  foo: 1,
  get bar() {
    return 2;
  },
};

let copy = Object.assign({}, obj);
console.log(copy);
// { foo: 1, bar: 2 }
// The value of copy.bar is obj.bar's getter's return value.

// This is an assign function that copies full descriptors
function completeAssign(target, ...sources) {
  sources.forEach((source) => {
    const descriptors = Object.keys(source).reduce((descriptors, key) => {
      descriptors[key] = Object.getOwnPropertyDescriptor(source, key);
      return descriptors;
    }, {});

    // By default, Object.assign copies enumerable Symbols, too
    Object.getOwnPropertySymbols(source).forEach((sym) => {
      const descriptor = Object.getOwnPropertyDescriptor(source, sym);
      if (descriptor.enumerable) {
        descriptors[sym] = descriptor;
      }
    });
    Object.defineProperties(target, descriptors);
  });
  return target;
}

copy = completeAssign({}, obj);
console.log(copy);
// { foo:1, get bar() { return 2 } }
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.assign]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.assign)

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

`assign`

45

12

34

32

9

45

34

32

9

5.0

45

1.0

4.0.0

 
See also 
--------

 
-   [Polyfill of `Object.assign` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-object)
-   [`Object.defineProperties()`](defineproperties)
-   [Enumerability and ownership of
    properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)
-   [Spread in object
    literals](../../operators/spread_syntax#spread_in_object_literals)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/assign>

