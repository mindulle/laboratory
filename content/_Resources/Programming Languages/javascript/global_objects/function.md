Function
========

 
The `Function` object provides methods for [functions](../functions). In
JavaScript, every function is actually a `Function` object.


 
Constructor
-----------

 

[`Function()`](function/function)

:   Creates a new `Function` object. Calling the constructor directly
    can create functions dynamically but suffers from security and
    similar (but far less significant) performance issues to
    [`eval()`](eval). However, unlike `eval()`, the `Function`
    constructor creates functions that execute in the global scope only.



 
Instance properties 
-------------------

 
These properties are defined on `Function.prototype` and shared by all
`Function` instances.

[`Function.prototype.arguments`](function/arguments) [Deprecated]

:   Represents the arguments passed to this function. For
    [strict](../strict_mode), arrow, async, and generator functions,
    accessing the `arguments` property throws a
    [`TypeError`](typeerror). Use the
    [`arguments`](../functions/arguments) object inside function
    closures instead.

[`Function.prototype.caller`](function/caller) [Deprecated]

:   Represents the function that invoked this function. For
    [strict](../strict_mode), arrow, async, and generator functions,
    accessing the `caller` property throws a [`TypeError`](typeerror).

[`Function.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `Function` instances, the initial value is the
    [`Function`](function/function) constructor.

These properties are own properties of each `Function` instance.

[`displayName`](function/displayname) [Non-standard]

:   The display name of the function.

[`length`](function/length)

:   Specifies the number of arguments expected by the function.

[`name`](function/name)

:   The name of the function.

[`prototype`](function/prototype)

:   Used when the function is used as a constructor with the
    [`new`](../operators/new) operator. It will become the new object\'s
    prototype.



 
Instance methods 
----------------

 

[`Function.prototype.apply()`](function/apply)

:   Calls a function with a given `this` value and optional arguments
    provided as an array (or an [array-like
    object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#working_with_array-like_objects)).

[`Function.prototype.bind()`](function/bind)

:   Creates a new function that, when called, has its `this` keyword set
    to a provided value, optionally with a given sequence of arguments
    preceding any provided when the new function is called.

[`Function.prototype.call()`](function/call)

:   Calls a function with a given `this` value and optional arguments.

[`Function.prototype.toString()`](function/tostring)

:   Returns a string representing the source code of the function.
    Overrides the [`Object.prototype.toString`](object/tostring) method.

[`Function.prototype[@@hasInstance]()`](function/@@hasinstance)

:   Specifies the default procedure for determining if a constructor
    function recognizes an object as one of the constructor\'s
    instances. Called by the [`instanceof`](../operators/instanceof)
    operator.



 
Examples
--------


 
### Difference between Function constructor and function declaration 

 
Functions created with the `Function` constructor do not create closures
to their creation contexts; they always are created in the global scope.
When running them, they will only be able to access their own local
variables and global ones, not the ones from the scope in which the
`Function` constructor was created. This is different from using
[`eval()`](eval) with code for a function expression.

 
 
[js]


```js
// Create a global property with `var`
var x = 10;

function createFunction1() {
  const x = 20;
  return new Function("return x;"); // this `x` refers to global `x`
}

function createFunction2() {
  const x = 20;
  function f() {
    return x; // this `x` refers to the local `x` above
  }
  return f;
}

const f1 = createFunction1();
console.log(f1()); // 10
const f2 = createFunction2();
console.log(f2()); // 20
```


While this code works in web browsers, `f1()` will produce a
`ReferenceError` in Node.js, as `x` will not be found. This is because
the top-level scope in Node is not the global scope, and `x` will be
local to the module.



Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-function-objects]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-function-objects)

  -----------------------------------------------------------------------------------------------------------------


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

`@@hasInstance`

50

15

50

37

10

50

50

37

10

5.0

50

1.0

6.5.0

`Function`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`Function`

1

12

1

3

1

18

4

10.1

1

1.0

≤37

1.0

0.10.0

`apply`

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

`arguments`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

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

`call`

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

0.10.0When calling this method, `thisArg` does not default to the global
object.

`caller`

1

12

1

9.6

3

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`displayName`

No

No

13

No

No

No

14

No

No

No

No

No

No

`length`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

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

`toString`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [`function`](../statements/function)
-   [`function` expression](../operators/function)
-   [`AsyncFunction`](asyncfunction)
-   [`AsyncGeneratorFunction`](asyncgeneratorfunction)
-   [`GeneratorFunction`](generatorfunction)
-   [Functions](../functions)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function>

