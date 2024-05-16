class
=====

Baseline [Widely available]
--------------------------------------

 
This feature is well established and works across many devices and
browser versions. It's been available across browsers since March 2017.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FStatements%2Fclass&level=high)


 
The `class` declaration creates a
[binding](https://developer.mozilla.org/en-US/docs/Glossary/Binding) of
a new [class](../classes) to a given name.

You can also define classes using the [`class`
expression](../operators/class).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
class name {
  // class body
}
class name extends otherName {
  // class body
}
```




 
Description
-----------

 
The class body of a class declaration is executed in [strict
mode](../strict_mode). The `class` declaration is very similar to
[`let`](let):

-   `class` declarations are scoped to blocks as well as functions.
-   `class` declarations can only be accessed after the place of
    declaration is reached (see [temporal dead
    zone](let#temporal_dead_zone_tdz)). For this reason, `class`
    declarations are commonly regarded as
    [non-hoisted](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting)
    (unlike [function declarations](function)).
-   `class` declarations do not create properties on
    [`globalThis`](../global_objects/globalthis) when declared at the
    top level of a script (unlike [function declarations](function)).
-   `class` declarations cannot be [redeclared](let#redeclarations) by
    any other declaration in the same scope.

Outside the class body, `class` declarations can be re-assigned like
`let`, but you should avoid doing so. Within the class body, the binding
is constant like `const`.

 
 
[js]


```js
class Foo {
  static {
    Foo = 1; // TypeError: Assignment to constant variable.
  }
}

class Foo2 {
  bar = (Foo2 = 1); // TypeError: Assignment to constant variable.
}

class Foo3 {}
Foo3 = 1;
console.log(Foo3); // 1
```




 
Examples
--------


 
### A simple class declaration 

 
In the following example, we first define a class named `Rectangle`,
then extend it to create a class named `FilledRectangle`.

Note that `super()`, used in the `constructor`, can only be used in
constructors, and *must* be called *before* the `this` keyword can be
used.

 
 
[js]


```js
class Rectangle {
  constructor(height, width) {
    this.name = "Rectangle";
    this.height = height;
    this.width = width;
  }
}

class FilledRectangle extends Rectangle {
  constructor(height, width, color) {
    super(height, width);
    this.name = "Filled rectangle";
    this.color = color;
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

`class`

49

42--49Strict mode is required.

13

45

36

29--36Strict mode is required.

10.1

49

42--49Strict mode is required.

45

36

29--36Strict mode is required.

10.3

5.0

4.0--5.0Strict mode is required.

49

42--49Strict mode is required.

1.0

6.0.0

 
See also 
--------

 
-   [`function`](function)
-   [`class` expression](../operators/class)
-   [Classes](../classes)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/class>

