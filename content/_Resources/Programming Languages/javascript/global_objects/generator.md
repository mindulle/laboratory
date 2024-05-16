Generator
=========

 
The `Generator` object is returned by a [generator
function](../statements/function*) and it conforms to both the [iterable
protocol](../iteration_protocols#the_iterable_protocol) and the
[iterator protocol](../iteration_protocols#the_iterator_protocol).

`Generator` is a subclass of the hidden [`Iterator`](iterator) class.


 
Try it 
------

 



 
Constructor
-----------

 
The `Generator` constructor is not available globally. Instances of
`Generator` must be returned from [generator
functions](../statements/function*):

 
 
[js]


```js
function* generator() {
  yield 1;
  yield 2;
  yield 3;
}

const gen = generator(); // "Generator { }"

console.log(gen.next().value); // 1
console.log(gen.next().value); // 2
console.log(gen.next().value); // 3
```


In fact, there\'s no JavaScript entity that corresponds to the
`Generator` constructor. There\'s only a hidden object which is the
prototype object shared by all objects created by generator functions.
This object is often stylized as `Generator.prototype` to make it look
like a class, but it should be more appropriately called
[`GeneratorFunction.prototype.prototype`](generatorfunction), because
`GeneratorFunction` is an actual JavaScript entity.



 
Instance properties 
-------------------

 
These properties are defined on `Generator.prototype` and shared by all
`Generator` instances.

[`Generator.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `Generator` instances, the initial value is
    [`GeneratorFunction.prototype`](generatorfunction).

     
    **Note:** `Generator` objects do not store a reference to the
    generator function that created them.
    

[`Generator.prototype[@@toStringTag]`](#generator.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"Generator"`. This property is used in
    [`Object.prototype.toString()`](object/tostring).



 
Instance methods 
----------------

 
*Also inherits instance methods from its parent [`Iterator`](iterator)*.

[`Generator.prototype.next()`](generator/next)

:   Returns a value yielded by the [`yield`](../operators/yield)
    expression.

[`Generator.prototype.return()`](generator/return)

:   Acts as if a `return` statement is inserted in the generator\'s body
    at the current suspended position, which finishes the generator and
    allows the generator to perform any cleanup tasks when combined with
    a [`try...finally`](../statements/try...catch#the_finally_block)
    block.

[`Generator.prototype.throw()`](generator/throw)

:   Acts as if a `throw` statement is inserted in the generator\'s body
    at the current suspended position, which informs the generator of an
    error condition and allows it to handle the error, or perform
    cleanup and close itself.



 
Examples
--------


 
### An infinite iterator 

 
With a generator function, values are not evaluated until they are
needed. Therefore a generator allows us to define a potentially infinite
data structure.

 
 
[js]


```js
function* infinite() {
  let index = 0;

  while (true) {
    yield index++;
  }
}

const generator = infinite(); // "Generator { }"

console.log(generator.next().value); // 0
console.log(generator.next().value); // 1
console.log(generator.next().value); // 2
// …
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-generator-objects]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-generator-objects)

  ---------------------------------------------------------------------------------------------------------------------------


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

`Generator`

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

`next`

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

`return`

50

13

38

37

10

50

38

37

10

5.0

50

1.0

6.0.0

`throw`

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
-   [`GeneratorFunction`](generatorfunction)
-   [Iteration protocols](../iteration_protocols)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator>

