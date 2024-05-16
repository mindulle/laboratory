Symbol.unscopables
==================

 
The `Symbol.unscopables` static data property represents the [well-known
symbol](../symbol#well-known_symbols) `@@unscopables`. The
[`with`](../../statements/with) statement looks up this symbol on the
scope object for a property containing a collection of properties that
should not become bindings within the `with` environment.


 
Try it 
------

 



 
Value
-----

 
The well-known symbol `@@unscopables`.

 
Property attributes of `Symbol.unscopables`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
The `@@unscopables` symbol (accessed via `Symbol.unscopables`) can be
defined on any object to exclude property names from being exposed as
lexical variables in [`with`](../../statements/with) environment
bindings. Note that when using [strict mode](../../strict_mode), `with`
statements are not available, and this symbol is likely not needed.

Setting a property of the `@@unscopables` object to `true` (or any
[truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
value) will make the corresponding property of the `with` scope object
*unscopable* and therefore won\'t be introduced to the `with` body
scope. Setting a property to `false` (or any
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) value)
will make it *scopable* and thus appear as lexical scope variables.

When deciding whether `x` is unscopable, the entire prototype chain of
the `@@unscopables` property is looked up for a property called `x`.
This means if you declared `@@unscopables` as a plain object,
`Object.prototype` properties like [`toString`](../object/tostring)
would become unscopable as well, which may cause backward
incompatibility for legacy code assuming those properties are normally
scoped (see [an example
below](#avoid_using_a_non-null-prototype_object_as_unscopables)). You
are advised to make your custom `@@unscopables` property have `null` as
its prototype, like
[`Array.prototype[@@unscopables]`](../array/@@unscopables) does.

This protocol is also utilized by DOM APIs, such as
[`Element.prototype.append()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/append).



 
Examples
--------


 
### Scoping in with statements 

 
The following code works fine in ES5 and below. However, in ECMAScript
2015 and later, the [`Array.prototype.keys()`](../array/keys) method was
introduced. That means that inside a `with` environment, \"keys\" would
now be the method and not the variable. That\'s why the `@@unscopables`
symbol was introduced. A built-in `@@unscopables` setting is implemented
as [`Array.prototype[@@unscopables]`](../array/@@unscopables) to prevent
some of the Array methods being scoped into the `with` statement.

 
 
[js]


```js
var keys = [];

with (Array.prototype) {
  keys.push("something");
}
```




 
### Unscopables in objects 

 
You can also set `@@unscopables` for your own objects.

 
 
[js]


```js
const obj = {
  foo: 1,
  bar: 2,
  baz: 3,
};

obj[Symbol.unscopables] = {
  // Make the object have `null` prototype to prevent
  // `Object.prototype` methods from being unscopable
  __proto__: null,
  // `foo` will be scopable
  foo: false,
  // `bar` will be unscopable
  bar: true,
  // `baz` is omitted; because `undefined` is falsy, it is also scopable (default)
};

with (obj) {
  console.log(foo); // 1
  console.log(bar); // ReferenceError: bar is not defined
  console.log(baz); // 3
}
```




 
### Avoid using a non-null-prototype object as @\@unscopables 

 
Declaring `@@unscopables` as a plain object without eliminating its
prototype may cause subtle bugs. Consider the following code working
before `@@unscopables`:

 
 
[js]


```js
const character = {
  name: "Yoda",
  toString: function () {
    return "Use with statements, you must not";
  },
};

with (character) {
  console.log(name + ' says: "' + toString() + '"'); // Yoda says: "Use with statements, you must not"
}
```


To preserve backward compatibility, you decided to add an
`@@unscopables` property when adding more properties to `character`. You
may naïvely do it like:

 
 
[js]


```js
const character = {
  name: "Yoda",
  toString: function () {
    return "Use with statements, you must not";
  },
  student: "Luke",
  [Symbol.unscopables]: {
    // Make `student` unscopable
    student: true,
  },
};
```


However, the code above now breaks:

 
 
[js]


```js
with (character) {
  console.log(name + ' says: "' + toString() + '"'); // Yoda says: "[object Undefined]"
}
```


This is because when looking up
`character[Symbol.unscopables].toString`, it returns
[`Object.prototype.toString()`](../object/tostring), which is a truthy
value, thus making the `toString()` call in the `with()` statement
reference `globalThis.toString()` instead --- and because it\'s called
without a [`this`](../../operators/this), `this` is `undefined`, making
it return `[object Undefined]`.

Even when the method is not overridden by `character`, making it
unscopable will change the value of `this`.

 
 
[js]


```js
const proto = {};
const obj = { __proto__: proto };

with (proto) {
  console.log(isPrototypeOf(obj)); // true; `isPrototypeOf` is scoped and `this` is `proto`
}

proto[Symbol.unscopables] = {};

with (proto) {
  console.log(isPrototypeOf(obj)); // TypeError: Cannot convert undefined or null to object
  // `isPrototypeOf` is unscoped and `this` is undefined
}
```


To fix this, always make sure `@@unscopables` only contains properties
you wish to be unscopable, without `Object.prototype` properties.

 
 
[js]


```js
const character = {
  name: "Yoda",
  toString: function () {
    return "Use with statements, you must not";
  },
  student: "Luke",
  [Symbol.unscopables]: {
    // Make the object have `null` prototype to prevent
    // `Object.prototype` methods from being unscopable
    __proto__: null,
    // Make `student` unscopable
    student: true,
  },
};
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.unscopables]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.unscopables)

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

`unscopables`

38

12

48

25

9

38

48

25

9

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [`Array.prototype[@@unscopables]`](../array/@@unscopables)
-   [`with`](../../statements/with)
-   [`Element.prototype.append()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/append)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/unscopables>

