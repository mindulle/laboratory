extends
=======

Baseline [Widely available]
--------------------------------------


This feature is well established and works across many devices and
browser versions. It's been available across browsers since March 2017.

- [Learn more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
- [See full compatibility](#browser_compatibility)
- [Report feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FClasses%2Fextends&level=high)



The `extends` keyword is used in [class declarations](../statements/class) or [class expressions](../operators/class) to create a class that is a child of another class.



Try it 
------






Syntax
------




[js]


```js
class ChildClass extends ParentClass { /* … */ }
```


[`ParentClass`](#parentclass)

:   An expression that evaluates to a constructor function (including a class) or `null`.




Description
-----------


The `extends` keyword can be used to subclass custom classes as well as
built-in objects.

Any constructor that can be called with [`new`](../operators/new) and
has the [`prototype`](../global_objects/function/prototype) property can
be the candidate for the parent class. The two conditions must both hold
--- for example, [bound functions](../global_objects/function/bind) and
[`Proxy`](../global_objects/proxy) can be constructed, but they don\'t
have a `prototype` property, so they cannot be subclassed.



[js]


```js
function OldStyleClass() {
  this.someProperty = 1;
}
OldStyleClass.prototype.someMethod = function () {};

class ChildClass extends OldStyleClass {}

class ModernClass {
  someProperty = 1;
  someMethod() {}
}

class AnotherChildClass extends ModernClass {}
```


The `prototype` property of the `ParentClass` must be an
[`Object`](../global_objects/object) or [`null`](../operators/null), but
you would rarely worry about this in practice, because a non-object
`prototype` doesn\'t behave as it should anyway. (It\'s ignored by the
[`new`](../operators/new) operator.)



[js]


```js
function ParentClass() {}
ParentClass.prototype = 3;

class ChildClass extends ParentClass {}
// Uncaught TypeError: Class extends value does not have valid prototype property 3

console.log(Object.getPrototypeOf(new ParentClass()));
// [Object: null prototype] {}
// Not actually a number!
```


`extends` sets the prototype for both `ChildClass` and
`ChildClass.prototype`.


                                      Prototype of `ChildClass`   Prototype of `ChildClass.prototype`
  ----------------------------------- --------------------------- -------------------------------------
  `extends` clause absent             `Function.prototype`        `Object.prototype`
  [`extends null`](#extending_null)   `Function.prototype`        `null`
  `extends ParentClass`               `ParentClass`               `ParentClass.prototype`




[js]


```js
class ParentClass {}
class ChildClass extends ParentClass {}

// Allows inheritance of static properties
Object.getPrototypeOf(ChildClass) === ParentClass;
// Allows inheritance of instance properties
Object.getPrototypeOf(ChildClass.prototype) === ParentClass.prototype;
```


The right-hand side of `extends` does not have to be an identifier. You
can use any expression that evaluates to a constructor. This is often
useful to create [mixins](#mix-ins). The `this` value in the `extends`
expression is the `this` surrounding the class definition, and referring
to the class\'s name is a
[`ReferenceError`](../global_objects/referenceerror) because the class
is not initialized yet. [`await`](../operators/await) and
[`yield`](../operators/yield) work as expected in this expression.



[js]


```js
class SomeClass extends class {
  constructor() {
    console.log("Base class");
  }
} {
  constructor() {
    super();
    console.log("Derived class");
  }
}

new SomeClass();
// Base class
// Derived class
```


While the base class may return anything from its constructor, the
derived class must return an object or `undefined`, or a
[`TypeError`](../global_objects/typeerror) will be thrown.



[js]


```js
class ParentClass {
  constructor() {
    return 1;
  }
}

console.log(new ParentClass()); // ParentClass {}
// The return value is ignored because it's not an object
// This is consistent with function constructors

class ChildClass extends ParentClass {
  constructor() {
    super();
    return 1;
  }
}

console.log(new ChildClass()); // TypeError: Derived constructors may only return object or undefined
```


If the parent class constructor returns an object, that object will be
used as the `this` value for the derived class when further initializing
[class fields](publicClassFields.md). This trick is called [](privateProperties.md#returning_overriding_object), which
allows a derived class\'s fields (including
[private](privateProperties.md) ones) to be defined on unrelated objects.




### Subclassing built-ins 


 
**Warning:** The standard committee now holds the position that the
built-in subclassing mechanism in previous spec versions is
over-engineered and causes non-negligible performance and security
impacts. New built-in methods consider less about subclasses, and engine
implementers are [investigating whether to remove certain subclassing
mechanisms](https://github.com/tc39/proposal-rm-builtin-subclassing).
Consider using composition instead of inheritance when enhancing
built-ins.


Here are some things you may expect when extending a class:

- When calling a static factory method (like [`Promise.resolve()`](../global_objects/promise/resolve) or [`Array.from()`](../global_objects/array/from)) on a subclass, the returned instance is always an instance of the subclass.
- When calling an instance method that returns a new instance (like    [`Promise.prototype.then()`](../global_objects/promise/then) or [`Array.prototype.map()`](../global_objects/array/map)) on a subclass, the returned instance is always an instance of the subclass.
- Instance methods try to delegate to a minimal set of primitive methods where possible. For example, for a subclass of [`Promise`](../global_objects/promise), overriding [`then()`](../global_objects/promise/then) automatically causes the behavior of [`catch()`](../global_objects/promise/catch) to change; or for a subclass of [`Map`](../global_objects/map), overriding    [`set()`](../global_objects/map/set) automatically causes the behavior of the [`Map()`](../global_objects/map/map) constructor to change.

However, the above expectations take non-trivial efforts to implement properly.

-   The first one requires the static method to read the value of
    [`this`](../operators/this) to get the constructor for constructing
    the returned instance. This means
    `[p1, p2, p3].map(Promise.resolve)` throws an error because the
    `this` inside `Promise.resolve` is `undefined`. A way to fix this is
    to fall back to the base class if `this` is not a constructor, like
    [`Array.from()`](../global_objects/array/from) does, but that still
    means the base class is special-cased.
-   The second one requires the instance method to read
    [`this.constructor`](../global_objects/object/constructor) to get
    the constructor function. However, `new this.constructor()` may
    break legacy code, because the `constructor` property is both
    writable and configurable and is not protected in any way.
    Therefore, many copying built-in methods use the constructor\'s
    [`@@species`](../global_objects/symbol/species) property instead
    (which by default just returns `this`, the constructor itself).
    However, `@@species` allows running arbitrary code and creating
    instances of arbitrary type, which poses a security concern and
    greatly complicates subclassing semantics.
-   The third one leads to visible invocations of custom code, which
    makes a lot of optimizations harder to implement. For example, if
    the `Map()` constructor is called with an iterable of *x* elements,
    then it must visibly invoke the `set()` method *x* times, instead of
    just copying the elements into the internal storage.

These problems are not unique to built-in classes. For your own classes,
you will likely have to make the same decisions. However, for built-in
classes, optimizability and security are a much bigger concern. New
built-in methods always construct the base class and call as few custom
methods as possible. If you want to subclass built-ins while achieving
the above expectations, you need to override all methods that have the
default behavior baked into them. Any addition of new methods on the
base class may also break the semantics of your subclass because they
are inherited by default. Therefore, a better way to extend built-ins is
to use [*composition*](#avoiding_inheritance).




### Extending null 


`extends null` was designed to allow easy creation of [objects that do
not inherit from
`Object.prototype`](../global_objects/object#null-prototype_objects).
However, due to unsettled decisions about whether `super()` should be
called within the constructor, it\'s not possible to construct such a
class in practice using any constructor implementation that doesn\'t
return an object. [The TC39 committee is working on re-enabling this
feature](https://github.com/tc39/ecma262/pull/1321).



[js]


```js
new (class extends null {})();
// TypeError: Super constructor null of anonymous class is not a constructor

new (class extends null {
  constructor() {}
})();
// ReferenceError: Must call super constructor in derived class before accessing 'this' or returning from derived constructor

new (class extends null {
  constructor() {
    super();
  }
})();
// TypeError: Super constructor null of anonymous class is not a constructor
```


Instead, you need to explicitly return an instance from the constructor.



[js]


```js
class NullClass extends null {
  constructor() {
    // Using new.target allows derived classes to
    // have the correct prototype chain
    return Object.create(new.target.prototype);
  }
}

const proto = Object.getPrototypeOf;
console.log(proto(proto(new NullClass()))); // null
```





Examples
--------



### Using extends 


The first example creates a class called `Square` from a class called
`Polygon`. This example is extracted from this [live
demo](https://googlechrome.github.io/samples/classes-es6/index.html)
[(source)](https://github.com/GoogleChrome/samples/blob/gh-pages/classes-es6/index.html).



[js]


```js
class Square extends Polygon {
  constructor(length) {
    // Here, it calls the parent class' constructor with lengths
    // provided for the Polygon's width and height
    super(length, length);
    // Note: In derived classes, super() must be called before you
    // can use 'this'. Leaving this out will cause a reference error.
    this.name = "Square";
  }

  get area() {
    return this.height * this.width;
  }
}
```





### Extending plain objects 


Classes cannot extend regular (non-constructible) objects. If you want
to inherit from a regular object by making all properties of this object
available on inherited instances, you can instead use
[`Object.setPrototypeOf()`](../global_objects/object/setprototypeof):



[js]


```js
const Animal = {
  speak() {
    console.log(`${this.name} makes a noise.`);
  },
};

class Dog {
  constructor(name) {
    this.name = name;
  }
}

Object.setPrototypeOf(Dog.prototype, Animal);

const d = new Dog("Mitzie");
d.speak(); // Mitzie makes a noise.
```





### Extending built-in objects 


This example extends the built-in [`Date`](../global_objects/date)
object. This example is extracted from this [live
demo](https://googlechrome.github.io/samples/classes-es6/index.html)
[(source)](https://github.com/GoogleChrome/samples/blob/gh-pages/classes-es6/index.html).



[js]


```js
class MyDate extends Date {
  getFormattedDate() {
    const months = [
      "Jan", "Feb", "Mar", "Apr", "May", "Jun",
      "Jul", "Aug", "Sep", "Oct", "Nov", "Dec",
    ];
    return `${this.getDate()}-${months[this.getMonth()]}-${this.getFullYear()}`;
  }
}
```





### Extending `Object` 


All JavaScript objects inherit from `Object.prototype` by default, so
writing `extends Object` at first glance seems redundant. The only
difference from not writing `extends` at all is that the constructor
itself inherits static methods from `Object`, such as
[`Object.keys()`](../global_objects/object/keys). However, because no
`Object` static method uses the `this` value, there\'s still no value in
inheriting these static methods.

The [`Object()`](../global_objects/object/object) constructor
special-cases the subclassing scenario. If it\'s implicitly called via
[`super()`](../operators/super), it always initializes a new object with
`new.target.prototype` as its prototype. Any value passed to `super()`
is ignored.



[js]


```js
class C extends Object {
  constructor(v) {
    super(v);
  }
}

console.log(new C(1) instanceof Number); // false
console.log(C.keys({ a: 1, b: 2 })); // [ 'a', 'b' ]
```


Compare this behavior with a custom wrapper that does not special-case
subclassing:



[js]


```js
function MyObject(v) {
  return new Object(v);
}
class D extends MyObject {
  constructor(v) {
    super(v);
  }
}
console.log(new D(1) instanceof Number); // true
```





### Species


You might want to return [`Array`](../global_objects/array) objects in
your derived array class `MyArray`. The species pattern lets you
override default constructors.

For example, when using methods such as
[`Array.prototype.map()`](../global_objects/array/map) that return the
default constructor, you want these methods to return a parent `Array`
object, instead of the `MyArray` object. The
[`Symbol.species`](../global_objects/symbol/species) symbol lets you do
this:



[js]


```js
class MyArray extends Array {
  // Overwrite species to the parent Array constructor
  static get [Symbol.species]() {
    return Array;
  }
}

const a = new MyArray(1, 2, 3);
const mapped = a.map((x) => x * x);

console.log(mapped instanceof MyArray); // false
console.log(mapped instanceof Array); // true
```


This behavior is implemented by many built-in copying methods. For
caveats of this feature, see the [subclassing
built-ins](#subclassing_built-ins) discussion.




### Mix-ins


Abstract subclasses or *mix-ins* are templates for classes. A class can
only have a single superclass, so multiple inheritance from tooling
classes, for example, is not possible. The functionality must be
provided by the superclass.

A function with a superclass as input and a subclass extending that
superclass as output can be used to implement mix-ins:



[js]


```js
const calculatorMixin = (Base) =>
  class extends Base {
    calc() {}
  };

const randomizerMixin = (Base) =>
  class extends Base {
    randomize() {}
  };
```


A class that uses these mix-ins can then be written like this:



[js]


```js
class Foo {}
class Bar extends calculatorMixin(randomizerMixin(Foo)) {}
```





### Avoiding inheritance 


Inheritance is a very strong coupling relationship in object-oriented
programming. It means all behaviors of the base class are inherited by
the subclass by default, which may not always be what you want. For
example, consider the implementation of a `ReadOnlyMap`:



[js]


```js
class ReadOnlyMap extends Map {
  set() {
    throw new TypeError("A read-only map must be set at construction time.");
  }
}
```


It turns out that `ReadOnlyMap` is not constructible, because the
[`Map()`](../global_objects/map/map) constructor calls the instance\'s
`set()` method.



[js]


```js
const m = new ReadOnlyMap([["a", 1]]); // TypeError: A read-only map must be set at construction time.
```


We may get around this by using a private flag to indicate whether the
instance is being constructed. However, a more significant problem with
this design is that it breaks the [Liskov substitution
principle](https://en.wikipedia.org/wiki/Liskov_substitution_principle),
which states that a subclass should be substitutable for its superclass.
If a function expects a `Map` object, it should be able to use a
`ReadOnlyMap` object as well, which will break here.

Inheritance often leads to [the circle-ellipse
problem](https://en.wikipedia.org/wiki/Circle%E2%80%93ellipse_problem),
because neither type perfectly entails the behavior of the other,
although they share a lot of common traits. In general, unless there\'s
a very good reason to use inheritance, it\'s better to use composition
instead. Composition means that a class has a reference to an object of
another class, and only uses that object as an implementation detail.



[js]


```js
class ReadOnlyMap {
  #data;
  constructor(values) {
    this.#data = new Map(values);
  }
  get(key) {
    return this.#data.get(key);
  }
  has(key) {
    return this.#data.has(key);
  }
  get size() {
    return this.#data.size;
  }
  *keys() {
    yield* this.#data.keys();
  }
  *values() {
    yield* this.#data.values();
  }
  *entries() {
    yield* this.#data.entries();
  }
  *[Symbol.iterator]() {
    yield* this.#data[Symbol.iterator]();
  }
}
```


In this case, the `ReadOnlyMap` class is not a subclass of `Map`, but it
still implements most of the same methods. This means more code
duplication, but it also means that the `ReadOnlyMap` class is not
strongly coupled to the `Map` class, and does not easily break if the
`Map` class is changed, avoiding the [semantic issues of built-in
subclassing](#subclassing_built-ins). For example, if the `Map` class
adds an [`emplace()`](https://github.com/tc39/proposal-upsert) method
that does not call `set()`, it would cause the `ReadOnlyMap` class to no
longer be read-only unless the latter is updated accordingly to override
`emplace()` as well. Moreover, `ReadOnlyMap` objects do not have the
`set` method at all, which is more accurate than throwing an error at
runtime.



Specifications
--------------


  -----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-class-definitions]](https://tc39.es/ecma262/multipage/ecmascript-language-functions-and-classes.html#sec-class-definitions)

  -----------------------------------------------------------------------------------------------------------------------------------------


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

`extends`

49

42--49Strict mode is required.

13

45

36

29--36Strict mode is required.

9

49

42--49Strict mode is required.

45

36

29--36Strict mode is required.

9

5.0

4.0--5.0Strict mode is required.

49

42--49Strict mode is required.

1.0

6.0.0


See also 
--------


-   [Using
    classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_classes)
    guide
-   [Classes](../classes)
-   [`constructor`](cnstr.md)
-   [`class`](../statements/class)
-   [`super`](../operators/super)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends>

