Object initializer
==================

 
An **object initializer** is a comma-delimited list of zero or more
pairs of property names and associated values of an object, enclosed in
curly braces (`{}`). Objects can also be initialized using
[`Object.create()`](../global_objects/object/create) or [by invoking a
constructor
function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_objects#using_a_constructor_function)
with the [`new`](new) operator.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
o = {
  a: "foo",
  b: 42,
  c: {},
  1: "number literal property",
  "foo:bar": "string literal property",

  shorthandProperty,

  method(parameters) {
    // …
  },

  get property() {},
  set property(value) {},

  [expression]: "computed property",

  __proto__: prototype,

  ...spreadProperty,
};
```




 
Description
-----------

 
An object initializer is an expression that describes the initialization
of an [`Object`](../global_objects/object). Objects consist of
*properties*, which are used to describe an object. The values of object
properties can either contain
[primitive](https://developer.mozilla.org/en-US/docs/Glossary/Primitive)
data types or other objects.



 
### Object literal syntax vs. JSON 

 
The object literal syntax is not the same as the **J**ava**S**cript
**O**bject **N**otation
([JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON)).
Although they look similar, there are differences between them:

-   JSON *only* permits property definition using the
    `"property": value` syntax. The property name must be double-quoted,
    and the definition cannot be a shorthand. Computed property names
    are not allowed either.
-   JSON object property values can only be strings, numbers, `true`,
    `false`, `null`, arrays, or another JSON object. This means JSON
    cannot express methods or non-plain objects like
    [`Date`](../global_objects/date) or
    [`RegExp`](../global_objects/regexp).
-   In JSON, `"__proto__"` is a normal property key. In an object
    literal, it [sets the object\'s prototype](#prototype_setter).

JSON is a *strict subset* of the object literal syntax, meaning that
every valid JSON text can be parsed as an object literal, and would
likely not cause syntax errors. The only exception is that the object
literal syntax prohibits duplicate `__proto__` keys, which does not
apply to [`JSON.parse()`](../global_objects/json/parse). The latter
treats `__proto__` like a normal property and takes the last occurrence
as the property\'s value. The only time when the object value they
represent (a.k.a. their semantic) differ is also when the source
contains the `__proto__` key --- for object literals, it sets the
object\'s prototype; for JSON, it\'s a normal property.

 
 
[js]


```js
console.log(JSON.parse('{ "__proto__": 0, "__proto__": 1 }')); // {__proto__: 1}
console.log({ "__proto__": 0, "__proto__": 1 }); // SyntaxError: Duplicate __proto__ fields are not allowed in object literals

console.log(JSON.parse('{ "__proto__": {} }')); // { __proto__: {} }
console.log({ "__proto__": {} }); // {} (with {} as prototype)
```




 
Examples
--------


 
### Creating objects 

 
An empty object with no properties can be created like this:

 
 
[js]


```js
const object = {};
```


However, the advantage of the *literal* or *initializer* notation is,
that you are able to quickly create objects with properties inside the
curly braces. You notate a list of `key: value` pairs delimited by
commas.

The following code creates an object with three properties and the keys
are `"foo"`, `"age"` and `"baz"`. The values of these keys are a string
`"bar"`, the number `42`, and another object.

 
 
[js]


```js
const object = {
  foo: "bar",
  age: 42,
  baz: { myProp: 12 },
};
```




 
### Accessing properties 

 
Once you have created an object, you might want to read or change them.
Object properties can be accessed by using the dot notation or the
bracket notation. (See [property accessors](property_accessors) for
detailed information.)

 
 
[js]


```js
object.foo; // "bar"
object["age"]; // 42
object.baz; // {myProp: 12}
object.baz.myProp; //12
```




 
### Property definitions 

 
We have already learned how to notate properties using the initializer
syntax. Oftentimes, there are variables in your code that you would like
to put into an object. You will see code like this:

 
 
[js]


```js
const a = "foo";
const b = 42;
const c = {};

const o = {
  a: a,
  b: b,
  c: c,
};
```


There is a shorter notation available to achieve the same:

 
 
[js]


```js
const a = "foo";
const b = 42;
const c = {};

// Shorthand property names
const o = { a, b, c };

// In other words,
console.log(o.a === { a }.a); // true
```


#### Duplicate property names 

When using the same name for your properties, the second property will
overwrite the first.

 
 
[js]


```js
const a = { x: 1, x: 2 };
console.log(a); // {x: 2}
```


After ES2015, duplicate property names are allowed everywhere, including
[strict mode](../strict_mode#duplicate_property_names). You can also
have duplicate property names in [classes](../classes). The only
exception is [private properties](privateProperties.md), which
must be unique in the class body.



 
### Method definitions 

 
A property of an object can also refer to a [function](../functions) or
a [getter](../functions/get) or [setter](../functions/set) method.

 
 
[js]


```js
const o = {
  property: function (parameters) {},
  get property() {},
  set property(value) {},
};
```


A shorthand notation is available, so that the keyword `function` is no
longer necessary.

 
 
[js]


```js
// Shorthand method names
const o = {
  property(parameters) {},
};
```


There is also a way to concisely define generator methods.

 
 
[js]


```js
const o = {
  *generator() {
    // …
  },
};
```


Which is equivalent to this ES5-like notation (but note that ECMAScript
5 has no generators):

 
 
[js]


```js
const o = {
  generator: function* () {
    // …
  },
};
```


For more information and examples about methods, see [method
definitions](../functions/method_definitions).



 
### Computed property names 

 
The object initializer syntax also supports computed property names.
That allows you to put an expression in square brackets `[]`, that will
be computed and used as the property name. This is reminiscent of the
bracket notation of the [property accessor](property_accessors) syntax,
which you may have used to read and set properties already.

Now you can use a similar syntax in object literals, too:

 
 
[js]


```js
// Computed property names
let i = 0;
const a = {
  [`foo${++i}`]: i,
  [`foo${++i}`]: i,
  [`foo${++i}`]: i,
};

console.log(a.foo1); // 1
console.log(a.foo2); // 2
console.log(a.foo3); // 3

const items = ["A", "B", "C"];
const obj = {
  [items]: "Hello",
};
console.log(obj); // A,B,C: "Hello"
console.log(obj["A,B,C"]); // "Hello"

const param = "size";
const config = {
  [param]: 12,
  [`mobile${param.charAt(0).toUpperCase()}${param.slice(1)}`]: 4,
};

console.log(config); // {size: 12, mobileSize: 4}
```




 
### Spread properties 

 
Object literals support the [spread syntax](spread_syntax). It copies
own enumerable properties from a provided object onto a new object.

Shallow-cloning (excluding `prototype`) or merging objects is now
possible using a shorter syntax than
[`Object.assign()`](../global_objects/object/assign).

 
 
[js]


```js
const obj1 = { foo: "bar", x: 42 };
const obj2 = { foo: "baz", y: 13 };

const clonedObj = { ...obj1 };
// { foo: "bar", x: 42 }

const mergedObj = { ...obj1, ...obj2 };
// { foo: "baz", x: 42, y: 13 }
```


 
**Warning:** Note that
[`Object.assign()`](../global_objects/object/assign) triggers
[setters](../functions/set), whereas the spread syntax doesn\'t!




 
### Prototype setter 

 
A property definition of the form `__proto__: value` or
`"__proto__": value` does not create a property with the name
`__proto__`. Instead, if the provided value is an object or
[`null`](null), it points the `[[Prototype]]` of the created object to
that value. (If the value is not an object or `null`, the object is not
changed.)

Note that the `__proto__` key is standardized syntax, in contrast to the
non-standard and non-performant
[`Object.prototype.__proto__`](../global_objects/object/proto)
accessors. It sets the `[[Prototype]]` during object creation, similar
to [`Object.create`](../global_objects/object/create) --- instead of
mutating the prototype chain.

 
 
[js]


```js
const obj1 = {};
console.log(Object.getPrototypeOf(obj1) === Object.prototype); // true

const obj2 = { __proto__: null };
console.log(Object.getPrototypeOf(obj2)); // null

const protoObj = {};
const obj3 = { "__proto__": protoObj };
console.log(Object.getPrototypeOf(obj3) === protoObj); // true

const obj4 = { __proto__: "not an object or null" };
console.log(Object.getPrototypeOf(obj4) === Object.prototype); // true
console.log(Object.hasOwn(obj4, "__proto__")); // false
```


Only a single prototype setter is permitted in an object literal.
Multiple prototype setters are a syntax error.

Property definitions that do not use \"colon\" notation are not
prototype setters. They are property definitions that behave identically
to similar definitions using any other name.

 
 
[js]


```js
const __proto__ = "variable";

const obj1 = { __proto__ };
console.log(Object.getPrototypeOf(obj1) === Object.prototype); // true
console.log(Object.hasOwn(obj1, "__proto__")); // true
console.log(obj1.__proto__); // "variable"

const obj2 = { __proto__() { return "hello"; } };
console.log(obj2.__proto__()); // "hello"

const obj3 = { ["__proto__"]: 17 };
console.log(obj3.__proto__); // 17

// Mixing prototype setter with normal own properties with "__proto__" key
const obj4 = { ["__proto__"]: 17, __proto__: {} }; // {__proto__: 17} (with {} as prototype)
const obj5 = {
  ["__proto__"]: 17,
  __proto__: {},
  __proto__: null, // SyntaxError: Duplicate __proto__ fields are not allowed in object literals
};
const obj6 = {
  ["__proto__"]: 17,
  ["__proto__"]: "hello",
  __proto__: null,
}; // {__proto__: "hello"} (with null as prototype)
const obj7 =  {
  ["__proto__"]: 17,
  __proto__,
  __proto__: null,
}; // {__proto__: "variable"} (with null as prototype)
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object-initializer]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#sec-object-initializer)

  ---------------------------------------------------------------------------------------------------------------------------------


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

`Object_initializer`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`computed_property_names`

47

12

34

34

8

47

34

34

8

5.0

47

?

4.0.0

`shorthand_method_names`

47

12

34

34

9

47

34

34

9

5.0

47

?

4.0.0

`shorthand_property_names`

47

12

33

34

9

47

33

34

9

5.0

47

?

4.0.0

`spread_properties`

60

79

55

47

11.1

60

55

44

11.3

8.0

60

?

8.3.0

 
See also 
--------

 
-   [Property accessors](property_accessors)
-   [`get`](../functions/get)
-   [`set`](../functions/set)
-   [Method definitions](../functions/method_definitions)
-   [Lexical grammar](../lexical_grammar)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer>

