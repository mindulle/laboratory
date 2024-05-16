Reflect.construct()
===================

 
The `Reflect.construct()` static method is like the
[`new`](../../operators/new) operator, but as a function. It is
equivalent to calling `new target(...args)`. It gives also the added
option to specify a different [`new.target`](../../operators/new.target)
value.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Reflect.construct(target, argumentsList)
Reflect.construct(target, argumentsList, newTarget)
```




 
### Parameters

 

[`target`](#target)

:   The target function to call.

[`argumentsList`](#argumentslist)

:   An [array-like
    object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#working_with_array-like_objects)
    specifying the arguments with which `target` should be called.

[`newTarget`](#newtarget) [Optional]

:   The value of [`new.target`](../../operators/new.target) operator,
    which usually specifies the prototype of the returned object. If
    `newTarget` is not present, its value defaults to `target`.



 
### Return value 

 
A new instance of `target` (or `newTarget`, if present), initialized by
`target` as a constructor with the given `argumentsList`.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `target` or `newTarget` is not a constructor, or if
    `argumentsList` is not an object.



 
Description
-----------

 
`Reflect.apply()` provides the reflective semantic of a constructor
call. That is, `Reflect.construct(target, argumentsList, newTarget)` is
semantically equivalent to:

 
 
[js]


```js
new target(...argumentsList);
```


Note that when using the `new` operator, `target` and `newTarget` are
always the same constructor --- but `Reflect.construct()` allows you to
pass a different [`new.target`](../../operators/new.target) value.
Conceptually, `newTarget` is the function on which `new` was called, and
`newTarget.prototype` will become the constructed object\'s prototype,
while `target` is the constructor that is actually executed to
initialize the object. For example, `new.target` may also be different
from the currently executed constructor in class inheritance.

 
 
[js]


```js
class A {
  constructor() {
    console.log(new.target.name);
  }
}
class B extends A {}

new B(); // "B"
```


`Reflect.construct()` allows you to invoke a constructor with a variable
number of arguments. (This is also possible with the [spread
syntax](../../operators/spread_syntax) in a normal constructor call.)

 
 
[js]


```js
const obj = new Foo(...args);
const obj = Reflect.construct(Foo, args);
```


`Reflect.construct()` invokes the `[[Construct]]` [object internal
method](../proxy#object_internal_methods) of `target`.



 
Examples
--------


 
### Using Reflect.construct() 

 
 
 
[js]


```js
const d = Reflect.construct(Date, [1776, 6, 4]);
d instanceof Date; // true
d.getFullYear(); // 1776
```




 
### Reflect.construct() vs. Object.create() 

 
Prior to the introduction of `Reflect`, objects could be constructed
using an arbitrary combination of constructors and prototypes using
[`Object.create()`](../object/create).

 
 
[js]


```js
function OneClass() {
  this.name = "one";
}

function OtherClass() {
  this.name = "other";
}

const obj2 = Object.create(OtherClass.prototype);
OneClass.apply(obj2, args);

console.log(obj1.name); // 'one'
console.log(obj2.name); // 'one'

console.log(obj1 instanceof OneClass); // false
console.log(obj2 instanceof OneClass); // false

console.log(obj1 instanceof OtherClass); // true
console.log(obj2 instanceof OtherClass); // true

// Another example to demonstrate below:

function func1(a, b, c, d) {
  console.log(arguments[3]);
}

function func2(d, e, f, g) {
  console.log(arguments[3]);
}

const obj1 = Reflect.construct(func1, ["I", "Love", "my", "country"]);
```


However, while the end result is the same, there is one important
difference in the process. When using `Object.create()` and
[`Function.prototype.apply()`](../function/apply), the `new.target`
operator will point to `undefined` within the function used as the
constructor, since the `new` keyword is not being used to create the
object. (In fact, it uses the [`apply`](apply) semantic, not
`construct`, although normal functions happen to operate nearly the
same.)

When invoking `Reflect.construct()`, on the other hand, the `new.target`
operator will point to the `newTarget` parameter if supplied, or
`target` if not.

 
 
[js]


```js
function OneClass() {
  console.log("OneClass");
  console.log(new.target);
}
function OtherClass() {
  console.log("OtherClass");
  console.log(new.target);
}

const obj1 = Reflect.construct(OneClass, args);
// Logs:
// OneClass
// function OneClass { ... }

const obj2 = Reflect.construct(OneClass, args, OtherClass);
// Logs:
// OneClass
// function OtherClass { ... }

const obj3 = Object.create(OtherClass.prototype);
OneClass.apply(obj3, args);
// Output:
//     OneClass
//     undefined
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-reflect.construct]](https://tc39.es/ecma262/multipage/reflection.html#sec-reflect.construct)

  ----------------------------------------------------------------------------------------------------------


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

`construct`

49

12

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

 
See also 
--------

 
-   [Polyfill of `Reflect.construct` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-reflect)
-   [`Reflect`](../reflect)
-   [`new`](../../operators/new)
-   [`new.target`](../../operators/new.target)
-   [`handler.construct()`](../proxy/proxy/construct)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/construct>

