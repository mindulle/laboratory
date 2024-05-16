GeneratorFunction() constructor
===============================

 
The `GeneratorFunction()` constructor creates
[`GeneratorFunction`](../generatorfunction) objects.

Note that `GeneratorFunction` is *not* a global object. It can be
obtained with the following code:

 
 
[js]


```js
const GeneratorFunction = function* () {}.constructor;
```


The `GeneratorFunction()` constructor is not intended to be used
directly, and all caveats mentioned in the
[`Function()`](../function/function) description apply to
`GeneratorFunction()`.


 
Syntax
------

 
 
 
[js]


```js
new GeneratorFunction(functionBody)
new GeneratorFunction(arg1, functionBody)
new GeneratorFunction(arg1, arg2, functionBody)
new GeneratorFunction(arg1, arg2, /* …, */ argN, functionBody)

GeneratorFunction(functionBody)
GeneratorFunction(arg1, functionBody)
GeneratorFunction(arg1, arg2, functionBody)
GeneratorFunction(arg1, arg2, /* …, */ argN, functionBody)
```


 
**Note:** `GeneratorFunction()` can be called with or without
[`new`](../../operators/new). Both create a new `GeneratorFunction`
instance.




 
### Parameters

 
See [`Function()`](../function/function).



 
Examples
--------


 
### Creating and using a GeneratorFunction() constructor 

 
 
 
[js]


```js
const GeneratorFunction = function* () {}.constructor;
const g = new GeneratorFunction("a", "yield a * 2");
const iterator = g(10);
console.log(iterator.next().value); // 20
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-generatorfunction-constructor]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-generatorfunction-constructor)

  ---------------------------------------------------------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [`function*`](../../statements/function*)
-   [`function*` expression](../../operators/function*)
-   [`Function()` constructor](../function/function)
-   [Iterators and
    generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators)
    guide
-   [Functions](../../functions)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/GeneratorFunction/GeneratorFunction>

