Classes
=======

Baseline [Widely available]
--------------------------------------

 
This feature is well established and works across many devices and
browser versions. It's been available across browsers since March 2017.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FClasses&level=high)


 
Classes are a template for creating objects. They encapsulate data with
code to work on that data. Classes in JS are built on
[prototypes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
but also have some syntax and semantics that are unique to classes.

For more examples and explanations, see the [Using
classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_classes)
guide.


 
Description
-----------


 
### Defining classes 

 
Classes are in fact \"special [functions](functions)\", and just as you
can define [function expressions](operators/function) and [function
declarations](statements/function), a class can be defined in two ways:
a [class expression](operators/class) or a [class
declaration](statements/class).

 
 
[js]


```js
// Declaration
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
}

// Expression; the class is anonymous but assigned to a variable
const Rectangle = class {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
};

// Expression; the class has its own name
const Rectangle = class Rectangle2 {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
};
```


Like function expressions, class expressions may be anonymous, or have a
name that\'s different from the variable that it\'s assigned to.
However, unlike function declarations, class declarations have the same
[temporal dead zone](statements/let#temporal_dead_zone_tdz) restrictions
as `let` or `const` and behave as if they are [not
hoisted](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_classes#class_declaration_hoisting).



 
### Class body 

 
The body of a class is the part that is in curly braces `{}`. This is
where you define class members, such as methods or constructor.

The body of a class is executed in [strict mode](strict_mode) even
without the `"use strict"` directive.

A class element can be characterized by three aspects:

-   Kind: Getter, setter, method, or field
-   Location: Static or instance
-   Visibility: Public or private

Together, they add up to 16 possible combinations. To divide the
reference more logically and avoid overlapping content, the different
elements are introduced in detail in different pages:

[Method definitions](functions/method_definitions)

:   Public instance method

[getter](functions/get)

:   Public instance getter

[setter](functions/set)

:   Public instance setter

[Public class fields](publicClassFields.md)

:   Public instance field

[`static`](classes/static)

:   Public static method, getter, setter, and field

[Private properties](privateProperties.md)

:   Everything that\'s private

 
**Note:** Private features have the restriction that all property names
declared in the same class must be unique. All other public properties
do not have this restriction --- you can have multiple public properties
with the same name, and the last one overwrites the others. This is the
same behavior as in [object
initializers](operators/object_initializer#duplicate_property_names).


In addition, there are two special class element syntaxes:
[`constructor`](#constructor) and [static initialization
blocks](#static_initialization_blocks), with their own references.

#### Constructor

The [`constructor`](cnstr.md) method is a special method for
creating and initializing an object created with a class. There can only
be one special method with the name \"constructor\" in a class --- a
[`SyntaxError`](global_objects/syntaxerror) is thrown if the class
contains more than one occurrence of a `constructor` method.

A constructor can use the [`super`](operators/super) keyword to call the
constructor of the super class.

You can create instance properties inside the constructor:

 
 
[js]


```js
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
}
```


Alternatively, if your instance properties\' values do not depend on the
constructor\'s arguments, you can define them as [class
fields](#field_declarations).

#### Static initialization blocks 

[Static initialization blocks](classes/static_initialization_blocks)
allow flexible initialization of [static
properties](#static_methods_and_fields), including the evaluation of
statements during initialization, while granting access to the private
scope.

Multiple static blocks can be declared, and these can be interleaved
with the declaration of static fields and methods (all static items are
evaluated in declaration order).

#### Methods

Methods are defined on the prototype of each class instance and are
shared by all instances. Methods can be plain functions, async
functions, generator functions, or async generator functions. For more
information, see [method definitions](functions/method_definitions).

 
 
[js]


```js
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
  // Getter
  get area() {
    return this.calcArea();
  }
  // Method
  calcArea() {
    return this.height * this.width;
  }
  *getSides() {
    yield this.height;
    yield this.width;
    yield this.height;
    yield this.width;
  }
}

const square = new Rectangle(10, 10);

console.log(square.area); // 100
console.log([...square.getSides()]); // [10, 10, 10, 10]
```


#### Static methods and fields 

The [`static`](classes/static) keyword defines a static method or field
for a class. Static properties (fields and methods) are defined on the
class itself instead of each instance. Static methods are often used to
create utility functions for an application, whereas static fields are
useful for caches, fixed-configuration, or any other data that doesn\'t
need to be replicated across instances.

 
 
[js]


```js
class Point {
  constructor(x, y) {
    this.x = x;
    this.y = y;
  }

  static displayName = "Point";
  static distance(a, b) {
    const dx = a.x - b.x;
    const dy = a.y - b.y;

    return Math.hypot(dx, dy);
  }
}

const p1 = new Point(5, 5);
const p2 = new Point(10, 10);
p1.displayName; // undefined
p1.distance; // undefined
p2.displayName; // undefined
p2.distance; // undefined

console.log(Point.displayName); // "Point"
console.log(Point.distance(p1, p2)); // 7.0710678118654755
```


#### Field declarations 

With the class field declaration syntax, the [constructor](#constructor)
example can be written as:

 
 
[js]


```js
class Rectangle {
  height = 0;
  width;
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
}
```


Class fields are similar to object properties, not variables, so we
don\'t use keywords such as `const` to declare them. In JavaScript,
[private features](#private_class_features) use a special identifier
syntax, so modifier keywords like `public` and `private` should not be
used either.

As seen above, the fields can be declared with or without a default
value. Fields without default values default to `undefined`. By
declaring fields up-front, class definitions become more
self-documenting, and the fields are always present, which help with
optimizations.

See [public class fields](publicClassFields.md) for more
information.

#### Private properties 

Using private fields, the definition can be refined as below.

 
 
[js]


```js
class Rectangle {
  #height = 0;
  #width;
  constructor(height, width) {
    this.#height = height;
    this.#width = width;
  }
}
```


It\'s an error to reference private fields from outside of the class;
they can only be read or written within the class body. By defining
things that are not visible outside of the class, you ensure that your
classes\' users can\'t depend on internals, which may change from
version to version.

Private fields can only be declared up-front in a field declaration.
They cannot be created later through assigning to them, the way that
normal properties can.

For more information, see [](privateProperties.md).



 
### Inheritance

 
The [`extends`](classes/extends) keyword is used in *class declarations*
or *class expressions* to create a class as a child of another
constructor (either a class or a function).

 
 
[js]


```js
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  constructor(name) {
    super(name); // call the super class constructor and pass in the name parameter
  }

  speak() {
    console.log(`${this.name} barks.`);
  }
}

const d = new Dog("Mitzie");
d.speak(); // Mitzie barks.
```


If there is a constructor present in the subclass, it needs to first
call `super()` before using `this`. The [`super`](operators/super)
keyword can also be used to call corresponding methods of super class.

 
 
[js]


```js
class Cat {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Lion extends Cat {
  speak() {
    super.speak();
    console.log(`${this.name} roars.`);
  }
}

const l = new Lion("Fuzzy");
l.speak();
// Fuzzy makes a noise.
// Fuzzy roars.
```




 
### Evaluation order 

 
When a [`class` declaration](statements/class) or [`class`
expression](operators/class) is evaluated, its various components are
evaluated in the following order:

1.  The [`extends`](classes/extends) clause, if present, is first
    evaluated. It must evaluate to a valid constructor function or
    `null`, or a [`TypeError`](global_objects/typeerror) is thrown.
2.  The [`constructor`](cnstr.md) method is extracted,
    substituted with a default implementation if `constructor` is not
    present. However, because the `constructor` definition is only a
    method definition, this step is not observable.
3.  The class elements\' property keys are evaluated in the order of
    declaration. If the property key is computed, the computed
    expression is evaluated, with the `this` value set to the `this`
    value surrounding the class (not the class itself). None of the
    property values are evaluated yet.
4.  Methods and accessors are installed in the order of declaration.
    Instance methods and accessors are installed on the `prototype`
    property of the current class, and static methods and accessors are
    installed on the class itself. Private instance methods and
    accessors are saved to be installed on the instance directly later.
    This step is not observable.
5.  The class is now initialized with the prototype specified by
    `extends` and implementation specified by `constructor`. For all
    steps above, if an evaluated expression tries to access the name of
    the class, a [`ReferenceError`](global_objects/referenceerror) is
    thrown because the class is not initialized yet.
6.  The class elements\' values are evaluated in the order of
    declaration:
    -   For each [instance field](publicClassFields.md) (public
        or private), its initializer expression is saved. The
        initializer is evaluated during instance creation, at the start
        of the constructor (for base classes) or immediately before the
        `super()` call returns (for derived classes).
    -   For each [static field](classes/static) (public or private), its
        initializer is evaluated with `this` set to the class itself,
        and the property is created on the class.
    -   [Static initialization
        blocks](classes/static_initialization_blocks) are evaluated with
        `this` set to the class itself.
7.  The class is now fully initialized and can be used as a constructor
    function.

For how instances are created, see the
[`constructor`](cnstr.md) reference.



 
Examples
--------


 
### Binding this with instance and static methods 

 
When a static or instance method is called without a value for
[`this`](operators/this), such as by assigning the method to a variable
and then calling it, the `this` value will be `undefined` inside the
method. This behavior is the same even if the
[`"use strict"`](strict_mode) directive isn\'t present, because code
within the `class` body is always executed in strict mode.

 
 
[js]


```js
class Animal {
  speak() {
    return this;
  }
  static eat() {
    return this;
  }
}

const obj = new Animal();
obj.speak(); // the Animal object
const speak = obj.speak;
speak(); // undefined

Animal.eat(); // class Animal
const eat = Animal.eat;
eat(); // undefined
```


If we rewrite the above using traditional function-based syntax in
non--strict mode, then `this` method calls are automatically bound to
[`globalThis`](global_objects/globalthis). In strict mode, the value of
`this` remains as `undefined`.

 
 
[js]


```js
function Animal() {}

Animal.prototype.speak = function () {
  return this;
};

Animal.eat = function () {
  return this;
};

const obj = new Animal();
const speak = obj.speak;
speak(); // global object (in non–strict mode)

const eat = Animal.eat;
eat(); // global object (in non-strict mode)
```




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

`Classes`

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

`constructor`

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

`private_class_fields`

74

79

90

62

14.1

74

90

53

14.5

11.0

74

1.0

12.0.0

`private_class_fields_in`

91

91

90

77

15

91

90

64

15

16.0

91

1.9

16.4.0

`private_class_methods`

84

84

90

70

15

84

90

60

15

14.0

84

1.0

14.6.0

`public_class_fields`

72

79

69

60

14.1

14--14.1Doesn\'t support public static fields. See [bug
194095](https://webkit.org/b/194095).

72

79

51

14.5

14--14.5Doesn\'t support public static fields. See [bug
194095](https://webkit.org/b/194095).

11.0

72

1.0

12.0.0

`static`

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

`static_class_fields`

72

79

75

60

14.1

72

79

51

14.5

11.0

72

1.0

12.0.0

`static_initialization_blocks`

94

94

93

80

16.4

94

93

66

16.4

17.0

94

1.14

16.11.0

 
See also 
--------

 
-   [Using
    classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_classes)
    guide
-   [`class`](statements/class)
-   [`class` expression](operators/class)
-   [Functions](functions)
-   [ES6 In Depth:
    Classes](https://hacks.mozilla.org/2015/07/es6-in-depth-classes/) on
    hacks.mozilla.org (2015)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes>

