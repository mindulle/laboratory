static
======

Baseline [Widely available]
--------------------------------------


This feature is well established and works across many devices and
browser versions. It's been available across browsers since March 2017.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FClasses%2Fstatic&level=high)



The `static` keyword defines a [static method or
field](../classes#static_methods_and_fields) for a class, or a [static
initialization block](static_initialization_blocks) (see the link for
more information about this usage). Static properties cannot be directly
accessed on instances of the class. Instead, they\'re accessed on the
class itself.

Static methods are often utility functions, such as functions to create
or clone objects, whereas static properties are useful for caches,
fixed-configuration, or any other data you don\'t need to be replicated
across instances.

 
**Note:** In the context of classes, MDN Web Docs content uses the terms
properties and [fields](publicClassFields.md) interchangeably.




Try it 
------






Syntax
------




[js]


```js
class ClassWithStatic {
  static staticField;
  static staticFieldWithInitializer = value;
  static staticMethod() {
    // …
  }
}
```


There are some additional syntax restrictions:

-   The name of a static property (field or method) cannot be
    `prototype`.
-   The name of a class field (static or instance) cannot be
    `constructor`.




Description
-----------


This page introduces public static properties of classes, which include
static methods, static accessors, and static fields.

-   For private static features, see [](privateProperties.md).
-   For instance features, see [methods
    definitions](../functions/method_definitions),
    [getter](../functions/get), [setter](../functions/set), and [](publicClassFields.md).

Public static features are declared using the `static` keyword. They are
added to the class constructor at the time of [class
evaluation](../classes#evaluation_order) using the
[`[[DefineOwnProperty]]`](../global_objects/proxy/proxy/defineproperty)
semantic (which is essentially
[`Object.defineProperty()`](../global_objects/object/defineproperty)).
They are accessed again from the class constructor.

Static methods are often utility functions, such as functions to create
or clone instances. Public static fields are useful when you want a
field to exist only once per class, not on every class instance you
create. This is useful for caches, fixed-configuration, or any other
data you don\'t need to be replicated across instances.

Static field names can be
[computed](../operators/object_initializer#computed_property_names). The
`this` value in the computed expression is the `this` surrounding the
class definition, and referring to the class\'s name is a
[`ReferenceError`](../global_objects/referenceerror) because the class
is not initialized yet. [`await`](../operators/await) and
[`yield`](../operators/yield) work as expected in this expression.

Static fields can have an initializer. Static fields without
initializers are initialized to `undefined`. Public static fields are
not reinitialized on subclasses, but can be accessed via the prototype
chain.



[js]


```js
class ClassWithStaticField {
  static staticField;
  static staticFieldWithInitializer = "static field";
}

class SubclassWithStaticField extends ClassWithStaticField {
  static subStaticField = "subclass field";
}

console.log(Object.hasOwn(ClassWithStaticField, "staticField")); // true
console.log(ClassWithStaticField.staticField); // undefined
console.log(ClassWithStaticField.staticFieldWithInitializer); // "static field"
console.log(SubclassWithStaticField.staticFieldWithInitializer); // "static field"
console.log(SubclassWithStaticField.subStaticField); // "subclass field"
```


In the field initializer, [`this`](../operators/this) refers to the
current class (which you can also access through its name), and
[`super`](../operators/super) refers to the base class constructor.



[js]


```js
class ClassWithStaticField {
  static baseStaticField = "base static field";
  static anotherBaseStaticField = this.baseStaticField;

  static baseStaticMethod() {
    return "base static method output";
  }
}

class SubClassWithStaticField extends ClassWithStaticField {
  static subStaticField = super.baseStaticMethod();
}

console.log(ClassWithStaticField.anotherBaseStaticField); // "base static field"
console.log(SubClassWithStaticField.subStaticField); // "base static method output"
```


The expression is evaluated synchronously. You cannot use
[`await`](../operators/await) or [`yield`](../operators/yield) in the
initializer expression. (Think of the initializer expression as being
implicitly wrapped in a function.)

Static field initializers and [static initialization
blocks](static_initialization_blocks) are evaluated one-by-one. Field
initializers can refer to field values above it, but not below it. All
static methods are added beforehand and can be accessed, although
calling them may not behave as expected if they refer to fields below
the one being initialized.

 
**Note:** This is more important with [](privateProperties.md), because accessing a non-initialized private
field throws a [`TypeError`](../global_objects/typeerror), even if the
private field is declared below. (If the private field is not declared,
it would be an early [`SyntaxError`](../global_objects/syntaxerror).)





Examples
--------



### Using static members in classes 


The following example demonstrates several things:

1.  How a static member (method or property) is defined on a class.
2.  That a class with a static member can be sub-classed.
3.  How a static member can and cannot be called.



[js]


```js
class Triple {
  static customName = "Tripler";
  static description = "I triple any number you provide";
  static calculate(n = 1) {
    return n * 3;
  }
}

class SquaredTriple extends Triple {
  static longDescription;
  static description = "I square the triple of any number you provide";
  static calculate(n) {
    return super.calculate(n) * super.calculate(n);
  }
}

console.log(Triple.description); // 'I triple any number you provide'
console.log(Triple.calculate()); // 3
console.log(Triple.calculate(6)); // 18

const tp = new Triple();

console.log(SquaredTriple.calculate(3)); // 81 (not affected by parent's instantiation)
console.log(SquaredTriple.description); // 'I square the triple of any number you provide'
console.log(SquaredTriple.longDescription); // undefined
console.log(SquaredTriple.customName); // 'Tripler'

// This throws because calculate() is a static member, not an instance member.
console.log(tp.calculate()); // 'tp.calculate is not a function'
```





### Calling static members from another static method 


In order to call a static method or property within another static
method of the same class, you can use the [`this`](../operators/this)
keyword.



[js]


```js
class StaticMethodCall {
  static staticProperty = "static property";
  static staticMethod() {
    return `Static method and ${this.staticProperty} has been called`;
  }
  static anotherStaticMethod() {
    return `${this.staticMethod()} from another static method`;
  }
}
StaticMethodCall.staticMethod();
// 'Static method and static property has been called'

StaticMethodCall.anotherStaticMethod();
// 'Static method and static property has been called from another static method'
```





### Calling static members from a class constructor and other methods 


Static members are not directly accessible using the
[`this`](../operators/this) keyword from non-static methods. You need to
call them using the class name: `CLASSNAME.STATIC_METHOD_NAME()` /
`CLASSNAME.STATIC_PROPERTY_NAME` or by calling the method as a property
of the `constructor`: `this.constructor.STATIC_METHOD_NAME()` /
`this.constructor.STATIC_PROPERTY_NAME`



[js]


```js
class StaticMethodCall {
  constructor() {
    console.log(StaticMethodCall.staticProperty); // 'static property'
    console.log(this.constructor.staticProperty); // 'static property'
    console.log(StaticMethodCall.staticMethod()); // 'static method has been called.'
    console.log(this.constructor.staticMethod()); // 'static method has been called.'
  }

  static staticProperty = "static property";
  static staticMethod() {
    return "static method has been called.";
  }
}
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


See also 
--------


-   [Using
    classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_classes)
    guide
-   [Classes](../classes)
-   [Static initialization blocks](static_initialization_blocks)
-   [`class`](../statements/class)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static

