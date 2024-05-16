function\*
==========

 
The `function*` declaration creates a
[binding](https://developer.mozilla.org/en-US/docs/Glossary/Binding) of
a new generator function to a given name. A generator function can be
exited and later re-entered, with its context (variable
[bindings](https://developer.mozilla.org/en-US/docs/Glossary/Binding))
saved across re-entrances.

You can also define generator functions using the [`function*`
expression](../operators/function*).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
function* name(param0) {
  statements
}
function* name(param0, param1) {
  statements
}
function* name(param0, param1, /* …, */ paramN) {
  statements
}
```


 
**Note:** Generator functions do not have arrow function counterparts.


 
**Note:** `function` and `*` are separate tokens, so they can be
separated by [whitespace or line
terminators](../lexical_grammar#white_space).




 
### Parameters

 

[`name`](#name)

:   The function name.

[`param`](#param) [Optional]

:   The name of a formal parameter for the function. For the
    parameters\' syntax, see the [Functions
    reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_parameters).

[`statements`](#statements) [Optional]

:   The statements comprising the body of the function.



 
Description
-----------

 
A `function*` declaration creates a
[`GeneratorFunction`](../global_objects/generatorfunction) object. Each
time when a generator function is called, it returns a new
[`Generator`](../global_objects/generator) object, which conforms to the
[iterator protocol](../iteration_protocols#the_iterator_protocol). When
the iterator\'s `next()` method is called, the generator function\'s
body is executed until the first [`yield`](../operators/yield)
expression, which specifies the value to be returned from the iterator
or, with [`yield*`](../operators/yield*), delegates to another generator
function. The `next()` method returns an object with a `value` property
containing the yielded value and a `done` property which indicates
whether the generator has yielded its last value, as a boolean. Calling
the `next()` method with an argument will resume the generator function
execution, replacing the `yield` expression where an execution was
paused with the argument from `next()`.

Generators in JavaScript --- especially when combined with Promises ---
are a very powerful tool for asynchronous programming as they mitigate
--- if not entirely eliminate \-- the problems with callbacks, such as
[Callback Hell](http://callbackhell.com/) and [Inversion of
Control](https://frontendmasters.com/courses/rethinking-async-js/callback-problems-inversion-of-control/).
However, an even simpler solution to these problems can be achieved with
[async functions](async_function).

A `return` statement in a generator, when executed, will make the
generator finish (i.e. the `done` property of the object returned by it
will be set to `true`). If a value is returned, it will be set as the
`value` property of the object returned by the generator. Much like a
`return` statement, an error thrown inside the generator will make the
generator finished --- unless caught within the generator\'s body. When
a generator is finished, subsequent `next()` calls will not execute any
of that generator\'s code, they will just return an object of this form:
`{value: undefined, done: true}`.

`function*` declarations behave similar to [`function`](function)
declarations --- they are
[hoisted](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting) to
the top of their scope and can be called anywhere in their scope, and
they can be redeclared only in certain contexts.



 
Examples
--------


 
### Simple example 

 
 
 
[js]


```js
function* idMaker() {
  let index = 0;
  while (true) {
    yield index++;
  }
}

const gen = idMaker();

console.log(gen.next().value); // 0
console.log(gen.next().value); // 1
console.log(gen.next().value); // 2
console.log(gen.next().value); // 3
// …
```




 
### Example with yield\* 

 
 
 
[js]


```js
function* anotherGenerator(i) {
  yield i + 1;
  yield i + 2;
  yield i + 3;
}

function* generator(i) {
  yield i;
  yield* anotherGenerator(i);
  yield i + 10;
}

const gen = generator(10);

console.log(gen.next().value); // 10
console.log(gen.next().value); // 11
console.log(gen.next().value); // 12
console.log(gen.next().value); // 13
console.log(gen.next().value); // 20
```




 
### Passing arguments into Generators 

 
 
 
[js]


```js
function* logGenerator() {
  console.log(0);
  console.log(1, yield);
  console.log(2, yield);
  console.log(3, yield);
}

const gen = logGenerator();

// the first call of next executes from the start of the function
// until the first yield statement
gen.next(); // 0
gen.next("pretzel"); // 1 pretzel
gen.next("california"); // 2 california
gen.next("mayonnaise"); // 3 mayonnaise
```




 
### Return statement in a generator 

 
 
 
[js]


```js
function* yieldAndReturn() {
  yield "Y";
  return "R";
  yield "unreachable";
}

const gen = yieldAndReturn();
console.log(gen.next()); // { value: "Y", done: false }
console.log(gen.next()); // { value: "R", done: true }
console.log(gen.next()); // { value: undefined, done: true }
```




 
### Generator as an object property 

 
 
 
[js]


```js
const someObj = {
  *generator() {
    yield "a";
    yield "b";
  },
};

const gen = someObj.generator();

console.log(gen.next()); // { value: 'a', done: false }
console.log(gen.next()); // { value: 'b', done: false }
console.log(gen.next()); // { value: undefined, done: true }
```




 
### Generator as an object method 

 
 
 
[js]


```js
class Foo {
  *generator() {
    yield 1;
    yield 2;
    yield 3;
  }
}

const f = new Foo();
const gen = f.generator();

console.log(gen.next()); // { value: 1, done: false }
console.log(gen.next()); // { value: 2, done: false }
console.log(gen.next()); // { value: 3, done: false }
console.log(gen.next()); // { value: undefined, done: true }
```




 
### Generator as a computed property 

 
 
 
[js]


```js
class Foo {
  *[Symbol.iterator]() {
    yield 1;
    yield 2;
  }
}

const SomeObj = {
  *[Symbol.iterator]() {
    yield "a";
    yield "b";
  },
};

console.log(Array.from(new Foo())); // [ 1, 2 ]
console.log(Array.from(SomeObj)); // [ 'a', 'b' ]
```




 
### Generators are not constructable 

 
 
 
[js]


```js
function* f() {}
const obj = new f(); // throws "TypeError: f is not a constructor
```




 
### Generator defined in an expression 

 
 
 
[js]


```js
const foo = function* () {
  yield 10;
  yield 20;
};

const bar = foo();
console.log(bar.next()); // {value: 10, done: false}
```




 
### Generator example 

 
 
 
[js]


```js
function* powers(n) {
  //endless loop to generate
  for (let current = n; ; current *= n) {
    yield current;
  }
}

for (const power of powers(2)) {
  // controlling generator
  if (power > 32) {
    break;
  }
  console.log(power);
  // 2
  // 4
  // 8
  // 16
  // 32
}
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-generator-function-definitions]](https://tc39.es/ecma262/multipage/ecmascript-language-functions-and-classes.html#sec-generator-function-definitions)

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`IteratorResult_object`

49

13

29

36

10

49

29

36

10

5.0

49

1.0

6.0.0

`function*`

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

`not_constructable_with_new`

50

13

43

37

10

50

43

37

10

5.0

50

1.0

6.0.0

`trailing_comma_in_parameters`

58

14

52

45

10

58

52

43

10

7.0

58

1.0

8.0.0

 
See also 
--------

 
-   [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
    guide
-   [Iterators and
    generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators)
    guide
-   [Functions](../functions)
-   [`GeneratorFunction`](../global_objects/generatorfunction)
-   [`function*` expression](../operators/function*)
-   [`function`](function)
-   [`async function`](async_function)
-   [`async function*`](async_function*)
-   [Iteration protocols](../iteration_protocols)
-   [`yield`](../operators/yield)
-   [`yield*`](../operators/yield*)
-   [`Generator`](../global_objects/generator)
-   [Regenerator](https://github.com/facebook/regenerator) on GitHub
-   [Promises and Generators: control flow
    utopia](https://youtu.be/qbKWsbJ76-s) presentation by Forbes
    Lindesay at JSConf (2013)
-   [Task.js](https://github.com/mozilla/task.js) on GitHub
-   [You Don\'t Know JS: Async & Performance, Ch.4:
    Generators](https://github.com/getify/You-Dont-Know-JS/blob/1st-ed/async%20%26%20performance/ch4.md)
    by Kyle Simpson



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*>

