Function.prototype.bind()
=========================

 
The `bind()` method of [`Function`](../function) instances creates a new
function that, when called, calls this function with its `this` keyword
set to the provided value, and a given sequence of arguments preceding
any provided when the new function is called.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
bind(thisArg)
bind(thisArg, arg1)
bind(thisArg, arg1, arg2)
bind(thisArg, arg1, arg2, /* …, */ argN)
```




 
### Parameters

 

[`thisArg`](#thisarg)

:   The value to be passed as the `this` parameter to the target
    function `func` when the bound function is called. If the function
    is not in [strict mode](../../strict_mode),
    [`null`](../../operators/null) and [`undefined`](../undefined) will
    be replaced with the global object, and primitive values will be
    converted to objects. The value is ignored if the bound function is
    constructed using the [`new`](../../operators/new) operator.

[`arg1`](#arg1), ..., `argN` [Optional]

:   Arguments to prepend to arguments provided to the bound function
    when invoking `func`.



 
### Return value 

 
A copy of the given function with the specified `this` value, and
initial arguments (if provided).



 
Description
-----------

 
The `bind()` function creates a new *bound function*. Calling the bound
function generally results in the execution of the function it wraps,
which is also called the *target function*. The bound function will
store the parameters passed --- which include the value of `this` and
the first few arguments --- as its internal state. These values are
stored in advance, instead of being passed at call time. You can
generally see `const boundFn = fn.bind(thisArg, arg1, arg2)` as being
equivalent to
`const boundFn = (...restArgs) => fn.call(thisArg, arg1, arg2, ...restArgs)`
for the effect when it\'s called (but not when `boundFn` is
constructed).

A bound function can be further bound by calling
`boundFn.bind(thisArg, /* more args */)`, which creates another bound
function `boundFn2`. The newly bound `thisArg` value is ignored, because
the target function of `boundFn2`, which is `boundFn`, already has a
bound `this`. When `boundFn2` is called, it would call `boundFn`, which
in turn calls `fn`. The arguments that `fn` ultimately receives are, in
order: the arguments bound by `boundFn`, arguments bound by `boundFn2`,
and the arguments received by `boundFn2`.

 
 
[js]


```js
"use strict"; // prevent `this` from being boxed into the wrapper object

function log(...args) {
  console.log(this, ...args);
}
const boundLog = log.bind("this value", 1, 2);
const boundLog2 = boundLog.bind("new this value", 3, 4);
boundLog2(5, 6); // "this value", 1, 2, 3, 4, 5, 6
```


A bound function may also be constructed using the
[`new`](../../operators/new) operator if its target function is
constructable. Doing so acts as though the target function had instead
been constructed. The prepended arguments are provided to the target
function as usual, while the provided `this` value is ignored (because
construction prepares its own `this`, as seen by the parameters of
[`Reflect.construct`](../reflect/construct)). If the bound function is
directly constructed, [`new.target`](../../operators/new.target) will be
the target function instead. (That is, the bound function is transparent
to `new.target`.)

 
 
[js]


```js
class Base {
  constructor(...args) {
    console.log(new.target === Base);
    console.log(args);
  }
}

const BoundBase = Base.bind(null, 1, 2);

new BoundBase(3, 4); // true, [1, 2, 3, 4]
```


However, because a bound function does not have the
[`prototype`](prototype) property, it cannot be used as a base class for
[`extends`](../../classes/extends).

 
 
[js]


```js
class Derived extends class {}.bind(null) {}
// TypeError: Class extends value does not have valid prototype property undefined
```


When using a bound function as the right-hand side of
[`instanceof`](../../operators/instanceof), `instanceof` would reach for
the target function (which is stored internally in the bound function)
and read its `prototype` instead.

 
 
[js]


```js
class Base {}
const BoundBase = Base.bind(null, 1, 2);
console.log(new Base() instanceof BoundBase); // true
```


The bound function has the following properties:

[`length`](length)

:   The `length` of the target function minus the number of arguments
    being bound (not counting the `thisArg` parameter), with 0 being the
    minimum value.

[`name`](name)

:   The `name` of the target function plus a `"bound "` prefix.

The bound function also inherits the [prototype
chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
of the target function. However, it doesn\'t have other own properties
of the target function (such as [static
properties](../../classes/static) if the target function is a class).



 
Examples
--------


 
### Creating a bound function 

 
The simplest use of `bind()` is to make a function that, no matter how
it is called, is called with a particular `this` value.

A common mistake for new JavaScript programmers is to extract a method
from an object, then to later call that function and expect it to use
the original object as its `this` (e.g., by using the method in
callback-based code).

Without special care, however, the original object is usually lost.
Creating a bound function from the function, using the original object,
neatly solves this problem:

 
 
[js]


```js
// Top-level 'this' is bound to 'globalThis' in scripts.
this.x = 9;
const module = {
  x: 81,
  getX() {
    return this.x;
  },
};

// The 'this' parameter of 'getX' is bound to 'module'.
console.log(module.getX()); // 81

const retrieveX = module.getX;
// The 'this' parameter of 'retrieveX' is bound to 'globalThis' in non-strict mode.
console.log(retrieveX()); // 9

// Create a new function 'boundGetX' with the 'this' parameter bound to 'module'.
const boundGetX = retrieveX.bind(module);
console.log(boundGetX()); // 81
```


 
**Note:** If you run this example in [strict mode](../../strict_mode),
the `this` parameter of `retrieveX` will be bound to `undefined` instead
of `globalThis`, causing the `retrieveX()` call to fail.

If you run this example in an ECMAScript module, top-level `this` will
be bound to `undefined` instead of `globalThis`, causing the
`this.x = 9` assignment to fail.

If you run this example in a Node CommonJS module, top-level `this` will
be bound to `module.exports` instead of `globalThis`. However, the
`this` parameter of `retrieveX` will still be bound to `globalThis` in
non-strict mode and to `undefined` in strict mode. Therefore, in
non-strict mode (the default), the `retrieveX()` call will return
`undefined` because `this.x = 9` is writing to a different object
(`module.exports`) from what `getX` is reading from (`globalThis`).


In fact, some built-in \"methods\" are also getters that return bound
functions --- one notable example being
[`Intl.NumberFormat.prototype.format()`](../intl/numberformat/format#using_format_with_map),
which, when accessed, returns a bound function that you can directly
pass as a callback.



 
### Partially applied functions 

 
The next simplest use of `bind()` is to make a function with
pre-specified initial arguments.

These arguments (if any) follow the provided `this` value and are then
inserted at the start of the arguments passed to the target function,
followed by whatever arguments are passed to the bound function at the
time it is called.

 
 
[js]


```js
function list(...args) {
  return args;
}

function addArguments(arg1, arg2) {
  return arg1 + arg2;
}

console.log(list(1, 2, 3)); // [1, 2, 3]

console.log(addArguments(1, 2)); // 3

// Create a function with a preset leading argument
const leadingThirtySevenList = list.bind(null, 37);

// Create a function with a preset first argument.
const addThirtySeven = addArguments.bind(null, 37);

console.log(leadingThirtySevenList()); // [37]
console.log(leadingThirtySevenList(1, 2, 3)); // [37, 1, 2, 3]
console.log(addThirtySeven(5)); // 42
console.log(addThirtySeven(5, 10)); // 42
// (the last argument 10 is ignored)
```




 
### With setTimeout() 

 
By default, within
[`setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/setTimeout),
the `this` keyword will be set to [`globalThis`](../globalthis), which
is [`window`](https://developer.mozilla.org/en-US/docs/Web/API/Window)
in browsers. When working with class methods that require `this` to
refer to class instances, you may explicitly bind `this` to the callback
function, in order to maintain the instance.

 
 
[js]


```js
class LateBloomer {
  constructor() {
    this.petalCount = Math.floor(Math.random() * 12) + 1;
  }
  bloom() {
    // Declare bloom after a delay of 1 second
    setTimeout(this.declare.bind(this), 1000);
  }
  declare() {
    console.log(`I am a beautiful flower with ${this.petalCount} petals!`);
  }
}

const flower = new LateBloomer();
flower.bloom();
// After 1 second, calls 'flower.declare()'
```


You can also use [arrow functions](../../functions/arrow_functions) for
this purpose.

 
 
[js]


```js
class LateBloomer {
  bloom() {
    // Declare bloom after a delay of 1 second
    setTimeout(() => this.declare(), 1000);
  }
}
```




 
### Bound functions used as constructors 

 
Bound functions are automatically suitable for use with the
[`new`](../../operators/new) operator to construct new instances created
by the target function. When a bound function is used to construct a
value, the provided `this` is ignored. However, provided arguments are
still prepended to the constructor call.

 
 
[js]


```js
function Point(x, y) {
  this.x = x;
  this.y = y;
}

Point.prototype.toString = function () {
  return `${this.x},${this.y}`;
};

const p = new Point(1, 2);
p.toString();
// '1,2'

// The thisArg's value doesn't matter because it's ignored
const YAxisPoint = Point.bind(null, 0 /*x*/);

const axisPoint = new YAxisPoint(5);
axisPoint.toString(); // '0,5'

axisPoint instanceof Point; // true
axisPoint instanceof YAxisPoint; // true
new YAxisPoint(17, 42) instanceof Point; // true
```


Note that you need not do anything special to create a bound function
for use with [`new`](../../operators/new).
[`new.target`](../../operators/new.target),
[`instanceof`](../../operators/instanceof),
[`this`](../../operators/this) etc. all work as expected, as if the
constructor was never bound. The only difference is that it can no
longer be used for [`extends`](../../classes/extends).

The corollary is that you need not do anything special to create a bound
function to be called plainly, even if you would rather require the
bound function to only be called using [`new`](../../operators/new). If
you call it without `new`, the bound `this` is suddenly not ignored.

 
 
[js]


```js
const emptyObj = {};
const YAxisPoint = Point.bind(emptyObj, 0 /*x*/);

// Can still be called as a normal function
// (although usually this is undesirable)
YAxisPoint(13);

// The modifications to `this` is now observable from the outside
console.log(emptyObj); // { x: 0, y: 13 }
```


If you wish to restrict a bound function to only be callable with
[`new`](../../operators/new), or only be callable without `new`, the
target function must enforce that restriction, such as by checking
`new.target !== undefined` or using a [class](../../classes) instead.



 
### Binding classes 

 
Using `bind()` on classes preserves most of the class\'s semantics,
except that all static own properties of the current class are lost.
However, because the prototype chain is preserved, you can still access
static properties inherited from the parent class.

 
 
[js]


```js
class Base {
  static baseProp = "base";
}

class Derived extends Base {
  static derivedProp = "derived";
}

const BoundDerived = Derived.bind(null);
console.log(BoundDerived.baseProp); // "base"
console.log(BoundDerived.derivedProp); // undefined
console.log(new BoundDerived() instanceof Derived); // true
```




 
### Transforming methods to utility functions 

 
`bind()` is also helpful in cases where you want to transform a method
which requires a specific `this` value to a plain utility function that
accepts the previous `this` parameter as a normal parameter. This is
similar to how general-purpose utility functions work: instead of
calling `array.map(callback)`, you use `map(array, callback)`, which
avoids mutating `Array.prototype`, and allows you to use `map` with
array-like objects that are not arrays (for example,
[`arguments`](../../functions/arguments)).

Take [`Array.prototype.slice()`](../array/slice), for example, which you
want to use for converting an array-like object to a real array. You
could create a shortcut like this:

 
 
[js]


```js
const slice = Array.prototype.slice;

// ...

slice.call(arguments);
```


Note that you can\'t save `slice.call` and call it as a plain function,
because the `call()` method also reads its `this` value, which is the
function it should call. In this case, you can use `bind()` to bind the
value of `this` for `call()`. In the following piece of code, `slice()`
is a bound version of [`Function.prototype.call()`](call), with the
`this` value bound to [`Array.prototype.slice()`](../array/slice). This
means that additional `call()` calls can be eliminated:

 
 
[js]


```js
// Same as "slice" in the previous example
const unboundSlice = Array.prototype.slice;
const slice = Function.prototype.call.bind(unboundSlice);

// ...

slice(arguments);
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-function.prototype.bind]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-function.prototype.bind)

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

`bind`

7

12

4

11.6

5.1

18

4

12

6

1.0

4

1.0

0.10.0

 
See also 
--------

 
-   [Polyfill of `Function.prototype.bind` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-function)
-   [`Function.prototype.apply()`](apply)
-   [`Function.prototype.call()`](call)
-   [Functions](../../functions)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind>

