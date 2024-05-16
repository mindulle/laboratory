GeneratorFunction
=================

 
The `GeneratorFunction` object provides methods for [generator
functions](../statements/function*). In JavaScript, every generator
function is actually a `GeneratorFunction` object.

Note that `GeneratorFunction` is *not* a global object. It can be
obtained with the following code:

 
 
[js]


```js
const GeneratorFunction = function* () {}.constructor;
```


`GeneratorFunction` is a subclass of [`Function`](function).


 
Try it 
------

 



 
Constructor
-----------

 

[`GeneratorFunction()`](generatorfunction/generatorfunction)

:   Creates a new `GeneratorFunction` object.



 
Instance properties 
-------------------

 
*Also inherits instance properties from its parent
[`Function`](function)*.

These properties are defined on `GeneratorFunction.prototype` and shared
by all `GeneratorFunction` instances.

[`GeneratorFunction.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `GeneratorFunction` instances, the initial value is the
    [`GeneratorFunction`](generatorfunction/generatorfunction)
    constructor.

[`GeneratorFunction.prototype.prototype`](#generatorfunction.prototype.prototype)

:   All generator functions share the same
    [`prototype`](function/prototype) property, which is
    [`Generator.prototype`](generator). Each generator function instance
    also has its own `prototype` property. When the generator function
    is called, the returned generator object inherits from the generator
    function\'s `prototype` property, which in turn inherits from
    `GeneratorFunction.prototype.prototype`.

[`GeneratorFunction.prototype[@@toStringTag]`](#generatorfunction.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"GeneratorFunction"`. This property is used
    in [`Object.prototype.toString()`](object/tostring).



 
Instance methods 
----------------

 
*Inherits instance methods from its parent [`Function`](function)*.



Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-generatorfunction-objects]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-generatorfunction-objects)

  -------------------------------------------------------------------------------------------------------------------------------------------


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

`GeneratorFunction`

39

13

26

26

10

39

26

26

10

4.0

39

1.0

4.0.0

`GeneratorFunction`

39

13

26

26

10

39

26

26

10

4.0

39

1.0

4.0.0

 
See also 
--------

 
-   [`function*`](../statements/function*)
-   [`function*` expression](../operators/function*)
-   [`Function`](function)
-   [`AsyncFunction`](asyncfunction)
-   [`AsyncGeneratorFunction`](asyncgeneratorfunction)
-   [Functions](../functions)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/GeneratorFunction>

