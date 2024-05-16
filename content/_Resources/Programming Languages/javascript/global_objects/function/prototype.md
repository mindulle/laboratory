Function: prototype
===================

 
The `prototype` data property of a [`Function`](../function) instance is
used when the function is used as a constructor with the
[`new`](../../operators/new) operator. It will become the new object\'s
prototype.

 
**Note:** Not all [`Function`](../function) objects have the `prototype`
property --- see [description](#description).



 
Value
-----

 
An object.

 
Property attributes of `Function: prototype`




Writable

yes

Enumerable

no

Configurable

no

 
**Note:** The `prototype` property of [classes](../../classes) is not
writable.


 
Description
-----------

 
When a function is called with [`new`](../../operators/new), the
constructor\'s `prototype` property will become the resulting object\'s
prototype.

 
 
[js]


```js
function Ctor() {}
const inst = new Ctor();
console.log(Object.getPrototypeOf(inst) === Ctor.prototype); // true
```


You can read [Inheritance and the prototype
chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain#constructors)
for more information about the interactions between a constructor
function\'s `prototype` property and the resulting object\'s prototype.

A function having a `prototype` property is not sufficient for it to be
eligible as a constructor. [Generator
functions](../../statements/function*) have a `prototype` property, but
cannot be called with `new`:

 
 
[js]


```js
async function* asyncGeneratorFunction() {}
function* generatorFunction() {}
```


Instead, generator functions\' `prototype` property is used when they
are called *without* `new`. The `prototype` property will become the
returned [`Generator`](../generator) object\'s prototype.

In addition, some functions may have a `prototype` but throw
unconditionally when called with `new`. For example, the
[`Symbol()`](../symbol/symbol) and [`BigInt()`](../bigint/bigint)
functions throw when called with `new`, because `Symbol.prototype` and
`BigInt.prototype` are only intended to provide methods for the
primitive values, but the wrapper objects should not be directly
constructed.

The following functions do not have `prototype`, and are therefore
ineligible as constructors, even if a `prototype` property is later
manually assigned:

 
 
[js]


```js
const method = { foo() {} }.foo;
const arrowFunction = () => {};
async function asyncFunction() {}
```


The following are valid constructors that have `prototype`:

 
 
[js]


```js
class Class {}
function fn() {}
```


A [bound function](bind) does not have a `prototype` property, but may
be constructable. When it\'s constructed, the target function is
constructed instead, and if the target function is constructable, it
would return a normal instance.

 
 
[js]


```js
const boundFunction = function () {}.bind(null);
```


A function\'s `prototype` property, by default, is a plain object with
one property: [`constructor`](../object/constructor), which is a
reference to the function itself. The `constructor` property is
writable, non-enumerable, and configurable.

If the `prototype` of a function is reassigned with something other than
an [`Object`](../object), when the function is called with `new`, the
returned object\'s prototype would be `Object.prototype` instead. (In
other words, `new` ignores the `prototype` property and constructs a
plain object.)

 
 
[js]


```js
function Ctor() {}
Ctor.prototype = 3;
console.log(Object.getPrototypeOf(new Ctor()) === Object.prototype); // true
```




 
Examples
--------


 
### Changing the prototype of all instances by mutating the prototype property 

 
 
 
[js]


```js
function Ctor() {}
const p1 = new Ctor();
const p2 = new Ctor();
Ctor.prototype.prop = 1;
console.log(p1.prop); // 1
console.log(p2.prop); // 1
```




 
### Adding a non-method property to a class\'s prototype property 

 
[Class fields](publicClassFields.md) add properties to each
instance. Class methods declare *function* properties on the prototype.
However, there\'s no way to add a non-function property to the
prototype. In case you want to share static data between all instances
(for example, [`Error.prototype.name`](../error/name) is the same
between all error instances), you can manually assign it on the
`prototype` of a class.

 
 
[js]


```js
class Dog {
  constructor(name) {
    this.name = name;
  }
}

Dog.prototype.species = "dog";

console.log(new Dog("Jack").species); // "dog"
```


This can be made more ergonomic using [static initialization
blocks](../../classes/static_initialization_blocks), which are called
when the class is initialized.

 
 
[js]


```js
class Dog {
  static {
    Dog.prototype.species = "dog";
  }
  constructor(name) {
    this.name = name;
  }
}

console.log(new Dog("Jack").species); // "dog"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-function-instances-prototype]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-function-instances-prototype)

  -----------------------------------------------------------------------------------------------------------------------------------------


 
See also 
--------

 
-   [`Function`](../function)
-   [Inheritance and the prototype
    chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain#constructors)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/prototype>

