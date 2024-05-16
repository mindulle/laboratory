Function: name
==============

 
The `name` data property of a [`Function`](../function) instance
indicates the function\'s name as specified when it was created, or it
may be either `anonymous` or `''` (an empty string) for functions
created anonymously.


 
Try it 
------

 



 
Value
-----

 
A string.

 
Property attributes of `Function: name`




Writable

no

Enumerable

no

Configurable

yes

 
**Note:** In non-standard, pre-ES2015 implementations the `configurable`
attribute was `false` as well.


 
Description
-----------

 
The function\'s `name` property can be used to identify the function in
debugging tools or error messages. It has no semantic significance to
the language itself.

The `name` property is read-only and cannot be changed by the assignment
operator:

 
 
[js]


```js
function someFunction() {}

someFunction.name = "otherFunction";
console.log(someFunction.name); // someFunction
```


To change it, use [`Object.defineProperty()`](../object/defineproperty).

The `name` property is typically inferred from how the function is
defined. In the following sections, we will describe the various ways in
which it can be inferred.



 
### Function declaration 

 
The `name` property returns the name of a function declaration.

 
 
[js]


```js
function doSomething() {}
doSomething.name; // "doSomething"
```




 
### Default-exported function declaration 

 
An [`export default`](../../statements/export) declaration exports the
function as a declaration instead of an expression. If the declaration
is anonymous, the name is `"default"`.

 
 
[js]


```js
// -- someModule.js --
export default function () {}

// -- main.js --
import someModule from "./someModule.js";

someModule.name; // "default"
```




 
### Function constructor 

 
Functions created with the [`Function()`](function) constructor have
name \"anonymous\".

 
 
[js]


```js
new Function().name; // "anonymous"
```




 
### Function expression 

 
If the function expression is named, that name is used as the `name`
property.

 
 
[js]


```js
const someFunction = function someFunctionName() {};
someFunction.name; // "someFunctionName"
```


Anonymous function expressions created using the keyword `function` or
arrow functions would have `""` (an empty string) as their name.

 
 
[js]


```js
(function () {}).name; // ""
(() => {}).name; // ""
```


However, such cases are rare --- usually, in order to refer to the
expression elsewhere, the function expression is attached to an
identifier when it\'s created (such as in a variable declaration). In
such cases, the name can be inferred, as the following few subsections
demonstrate.

One practical case where the name cannot be inferred is a function
returned from another function:

 
 
[js]


```js
function getFoo() {
  return () => {};
}
getFoo().name; // ""
```




 
### Variable declaration and method 

 
Variables and methods can infer the name of an anonymous function from
its syntactic position.

 
 
[js]


```js
const f = function () {};
const object = {
  someMethod: function () {},
};

console.log(f.name); // "f"
console.log(object.someMethod.name); // "someMethod"
```


The same applies to assignment:

 
 
[js]


```js
let f;
f = () => {};
f.name; // "f"
```




 
### Initializer and default value 

 
Functions in initializers (default values) of
[destructuring](../../operators/destructuring_assignment#default_value),
[default parameters](../../functions/default_parameters), [](publicClassFields.md), etc., will inherit the name
of the bound identifier as their `name`.

 
 
[js]


```js
const [f = () => {}] = [];
f.name; // "f"

const { someMethod: m = () => {} } = {};
m.name; // "m"

function foo(f = () => {}) {
  console.log(f.name);
}
foo(); // "f"

class Foo {
  static someMethod = () => {};
}
Foo.someMethod.name; // someMethod
```




 
### Shorthand method 

 
 
 
[js]


```js
const o = {
  foo() {},
};
o.foo.name; // "foo";
```




 
### Bound function 

 
[`Function.prototype.bind()`](bind) produces a function whose name is
\"bound \" plus the function name.

 
 
[js]


```js
function foo() {}
foo.bind({}).name; // "bound foo"
```




 
### Getter and setter 

 
When using [`get`](../../functions/get) and [`set`](../../functions/set)
accessor properties, \"get\" or \"set\" will appear in the function
name.

 
 
[js]


```js
const o = {
  get foo() {},
  set foo(x) {},
};

const descriptor = Object.getOwnPropertyDescriptor(o, "foo");
descriptor.get.name; // "get foo"
descriptor.set.name; // "set foo";
```




 
### Class

 
A class\'s name follows the same algorithm as function declarations and
expressions.

 
 
[js]


```js
class Foo {}
Foo.name; // "Foo"
```


 
**Warning:** JavaScript will set the function\'s `name` property only if
a function does not have an own property called `name`. However,
classes\' [static members](../../classes/static) will be set as own
properties of the class constructor function, and thus prevent the
built-in `name` from being applied. See [an
example](#telling_the_constructor_name_of_an_object) below.




 
### Symbol as function name 

 
If a [`Symbol`](../symbol) is used a function name and the symbol has a
description, the method\'s name is the description in square brackets.

 
 
[js]


```js
const sym1 = Symbol("foo");
const sym2 = Symbol();

const o = {
  [sym1]() {},
  [sym2]() {},
};

o[sym1].name; // "[foo]"
o[sym2].name; // "[]"
```




 
### Private property 

 
Private fields and private methods have the hash (`#`) as part of their
names.

 
 
[js]


```js
class Foo {
  #field = () => {};
  #method() {}
  getNames() {
    console.log(this.#field.name);
    console.log(this.#method.name);
  }
}

new Foo().getNames();
// "#field"
// "#method"
```




 
Examples
--------


 
### Telling the constructor name of an object 

 
You can use `obj.constructor.name` to check the \"class\" of an object.

 
 
[js]


```js
function Foo() {} // Or: class Foo {}

const fooInstance = new Foo();
console.log(fooInstance.constructor.name); // "Foo"
```


However, because static members will become own properties of the class,
we can\'t obtain the class name for virtually any class with a static
method property `name()`:

 
 
[js]


```js
class Foo {
  constructor() {}
  static name() {}
}
```


With a `static name()` method `Foo.name` no longer holds the actual
class name but a reference to the `name()` function object. Trying to
obtain the class of `fooInstance` via `fooInstance.constructor.name`
won\'t give us the class name at all, but instead a reference to the
static class method. Example:

 
 
[js]


```js
const fooInstance = new Foo();
console.log(fooInstance.constructor.name); // ƒ name() {}
```


Due to the existence of static fields, `name` may not be a function
either.

 
 
[js]


```js
class Foo {
  static name = 123;
}
console.log(new Foo().constructor.name); // 123
```


If a class has a static property called `name`, it will also become
*writable*. The built-in definition in the absence of a custom static
definition is *read-only*:

 
 
[js]


```js
Foo.name = "Hello";
console.log(Foo.name); // "Hello" if class Foo has a static "name" property, but "Foo" if not.
```


Therefore you may not rely on the built-in `name` property to always
hold a class\'s name.



 
### JavaScript compressors and minifiers 

 
 
**Warning:** Be careful when using the `name` property with source-code
transformations, such as those carried out by JavaScript compressors
(minifiers) or obfuscators. These tools are often used as part of a
JavaScript build pipeline to reduce the size of a program prior to
deploying it to production. Such transformations often change a
function\'s name at build time.


Source code such as:

 
 
[js]


```js
function Foo() {}
const foo = new Foo();

if (foo.constructor.name === "Foo") {
  console.log("'foo' is an instance of 'Foo'");
} else {
  console.log("Oops!");
}
```


may be compressed to:

 
 
[js]


```js
function a() {}
const b = new a();
if (b.constructor.name === "Foo") {
  console.log("'foo' is an instance of 'Foo'");
} else {
  console.log("Oops!");
}
```


In the uncompressed version, the program runs into the truthy branch and
logs \"\'foo\' is an instance of \'Foo\'\" --- whereas, in the
compressed version it behaves differently, and runs into the else
branch. If you rely on the `name` property, like in the example above,
make sure your build pipeline doesn\'t change function names, or don\'t
assume a function has a particular name.



Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-function-instances-name]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-function-instances-name)

  -------------------------------------------------------------------------------------------------------------------------------


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

`name`

15

14

1

10.5

6

18

4

11

6

1.0

4.4

1.0

0.10.0

`configurable_true`

43

14

38

30

10

43

38

30

10

4.0

43

1.0

4.0.0

`inferred_names`

51

79

14--79Names for functions defined in a dictionary are properly assigned;
however, anonymous functions defined on a var/let variable assignment
have blank names.

53

38

10

51

53

41

10

5.0

51

1.0

6.5.0

 
See also 
--------

 
-   [Polyfill for `Function: name` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-function)
-   [`Function`](../function)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/name>

