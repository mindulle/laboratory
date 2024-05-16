class expression
================

 
The `class` keyword can be used to define a class inside an expression.

You can also define classes using the [`class`
declaration](../statements/class).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
class {
  // class body
}
class name {
  // class body
}
```


 
**Note:** An [expression statement](../statements/expression_statement)
cannot begin with the keyword `class` to avoid ambiguity with a [`class`
declaration](../statements/class). The `class` keyword only begins an
expression when it appears in a context that cannot accept statements.




 
Description
-----------

 
A `class` expression is very similar to, and has almost the same syntax
as, a [`class` declaration](../statements/class). As with `class`
declarations, the body of a `class` expression is executed in [strict
mode](../strict_mode). The main difference between a `class` expression
and a `class` declaration is the *class name*, which can be omitted in
`class` expressions to create *anonymous* classes. Class expressions
allow you to redefine classes, while redeclaring a class using `class`
declarations throws a [`SyntaxError`](../global_objects/syntaxerror).
See also the chapter about [classes](../classes) for more information.



 
Examples
--------


 
### A simple class expression 

 
This is just a simple anonymous class expression which you can refer to
using the variable `Foo`.

 
 
[js]


```js
const Foo = class {
  constructor() {}
  bar() {
    return "Hello World!";
  }
};

const instance = new Foo();
instance.bar(); // "Hello World!"
Foo.name; // "Foo"
```




 
### Named class expressions 

 
If you want to refer to the current class inside the class body, you can
create a *named class expression*. The name is only visible within the
scope of the class expression itself.

 
 
[js]


```js
const Foo = class NamedFoo {
  constructor() {}
  whoIsThere() {
    return NamedFoo.name;
  }
};
const bar = new Foo();
bar.whoIsThere(); // "NamedFoo"
NamedFoo.name; // ReferenceError: NamedFoo is not defined
Foo.name; // "NamedFoo"
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

42

13

45

29

7

42

45

29

7

4.0

42

1.0

6.0.0

 
See also 
--------

 
-   [`class`](../statements/class)
-   [Classes](../classes)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/class>

