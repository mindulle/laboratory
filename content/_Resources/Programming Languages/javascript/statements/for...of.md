for\...of
=========

 
The `for...of` statement executes a loop that operates on a sequence of
values sourced from an [iterable
object](../iteration_protocols#the_iterable_protocol). Iterable objects
include instances of built-ins such as
[`Array`](../global_objects/array),
[`String`](../global_objects/string),
[`TypedArray`](../global_objects/typedarray),
[`Map`](../global_objects/map), [`Set`](../global_objects/set),
[`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)
(and other DOM collections), as well as the
[`arguments`](../functions/arguments) object,
[generators](../global_objects/generator) produced by [generator
functions](function*), and user-defined iterables.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
for (variable of iterable)
  statement
```


[`variable`](#variable)

:   Receives a value from the sequence on each iteration. May be either
    a declaration with [`const`](const), [`let`](let), or [`var`](var),
    or an [assignment](../operators/assignment) target (e.g. a
    previously declared variable, an object property, or a
    [destructuring assignment
    pattern](../operators/destructuring_assignment)). Variables declared
    with `var` are not local to the loop, i.e. they are in the same
    scope the `for...of` loop is in.

[`iterable`](#iterable)

:   An iterable object. The source of the sequence of values on which
    the loop operates.

[`statement`](#statement)

:   A statement to be executed on every iteration. May reference
    `variable`. You can use a [block statement](block) to execute
    multiple statements.



 
Description
-----------

 
A `for...of` loop operates on the values sourced from an iterable one by
one in sequential order. Each operation of the loop on a value is called
an *iteration*, and the loop is said to *iterate over the iterable*.
Each iteration executes statements that may refer to the current
sequence value.

When a `for...of` loop iterates over an iterable, it first calls the
iterable\'s [`[@@iterator]()`](../global_objects/symbol/iterator)
method, which returns an
[iterator](../iteration_protocols#the_iterator_protocol), and then
repeatedly calls the resulting iterator\'s
[`next()`](../iteration_protocols#the_iterator_protocol) method to
produce the sequence of values to be assigned to `variable`.

A `for...of` loop exits when the iterator has completed (the iterator\'s
`next()` method returns an object containing `done: true`). You may also
use control flow statements to change the normal control flow.
[`break`](break) exits the loop and goes to the first statement after
the loop body, while [`continue`](continue) skips the rest of the
statements of the current iteration and proceeds to the next iteration.

If the `for...of` loop exited early (e.g. a `break` statement is
encountered or an error is thrown), the
[`return()`](../iteration_protocols#the_iterator_protocol) method of the
iterator is called to perform any cleanup.

The `variable` part of `for...of` accepts anything that can come before
the `=` operator. You can use [`const`](const) to declare the variable
as long as it\'s not reassigned within the loop body (it can change
between iterations, because those are two separate variables).
Otherwise, you can use [`let`](let).

 
 
[js]


```js
const iterable = [10, 20, 30];

for (let value of iterable) {
  value += 1;
  console.log(value);
}
// 11
// 21
// 31
```


 
**Note:** Each iteration creates a new variable. Reassigning the
variable inside the loop body does not affect the original value in the
iterable (an array, in this case).


You can use [destructuring](../operators/destructuring_assignment) to
assign multiple local variables, or use a property accessor like
`for (x.y of iterable)` to assign the value to an object property.

However, a special rule forbids using `async` as the variable name. This
is invalid syntax:

 
 
[js]


```js
let async;
for (async of [1, 2, 3]); // SyntaxError: The left-hand side of a for-of loop may not be 'async'.
```


This is to avoid syntax ambiguity with the valid code
`for (async of => {};;)`, which is a [`for`](for) loop.



 
Examples
--------


 
### Iterating over an Array 

 
 
 
[js]


```js
const iterable = [10, 20, 30];

for (const value of iterable) {
  console.log(value);
}
// 10
// 20
// 30
```




 
### Iterating over a string 

 
Strings are [iterated by Unicode code
points](../global_objects/string/@@iterator).

 
 
[js]


```js
const iterable = "boo";

for (const value of iterable) {
  console.log(value);
}
// "b"
// "o"
// "o"
```




 
### Iterating over a TypedArray 

 
 
 
[js]


```js
const iterable = new Uint8Array([0x00, 0xff]);

for (const value of iterable) {
  console.log(value);
}
// 0
// 255
```




 
### Iterating over a Map 

 
 
 
[js]


```js
const iterable = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);

for (const entry of iterable) {
  console.log(entry);
}
// ['a', 1]
// ['b', 2]
// ['c', 3]

for (const [key, value] of iterable) {
  console.log(value);
}
// 1
// 2
// 3
```




 
### Iterating over a Set 

 
 
 
[js]


```js
const iterable = new Set([1, 1, 2, 2, 3, 3]);

for (const value of iterable) {
  console.log(value);
}
// 1
// 2
// 3
```




 
### Iterating over the arguments object 

 
You can iterate over the [`arguments`](../functions/arguments) object to
examine all parameters passed into a function.

 
 
[js]


```js
function foo() {
  for (const value of arguments) {
    console.log(value);
  }
}

foo(1, 2, 3);
// 1
// 2
// 3
```




 
### Iterating over a NodeList 

 
The following example adds a `read` class to paragraphs that are direct
descendants of the
[`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article)
element by iterating over a
[`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)
DOM collection.

 
 
[js]


```js
const articleParagraphs = document.querySelectorAll("article > p");
for (const paragraph of articleParagraphs) {
  paragraph.classList.add("read");
}
```




 
### Iterating over a user-defined iterable 

 
Iterating over an object with an `@@iterator` method that returns a
custom iterator:

 
 
[js]


```js
const iterable = {
  [Symbol.iterator]() {
    let i = 1;
    return {
      next() {
        if (i <= 3) {
          return { value: i++, done: false };
        }
        return { value: undefined, done: true };
      },
    };
  },
};

for (const value of iterable) {
  console.log(value);
}
// 1
// 2
// 3
```


Iterating over an object with an `@@iterator` generator method:

 
 
[js]


```js
const iterable = {
  *[Symbol.iterator]() {
    yield 1;
    yield 2;
    yield 3;
  },
};

for (const value of iterable) {
  console.log(value);
}
// 1
// 2
// 3
```


*Iterable iterators* (iterators with a `[@@iterator]()` method that
returns `this`) are a fairly common technique to make iterators usable
in syntaxes expecting iterables, such as `for...of`.

 
 
[js]


```js
let i = 1;

const iterator = {
  next() {
    if (i <= 3) {
      return { value: i++, done: false };
    }
    return { value: undefined, done: true };
  },
  [Symbol.iterator]() {
    return this;
  },
};

for (const value of iterator) {
  console.log(value);
}
// 1
// 2
// 3
```




 
### Iterating over a generator 

 
 
 
[js]


```js
function* source() {
  yield 1;
  yield 2;
  yield 3;
}

const generator = source();

for (const value of generator) {
  console.log(value);
}
// 1
// 2
// 3
```




 
### Early exiting 

 
Execution of the `break` statement in the first loop causes it to exit
early. The iterator is not finished yet, so the second loop will
continue from where the first one stopped at.

 
 
[js]


```js
const source = [1, 2, 3];

const iterator = source[Symbol.iterator]();

for (const value of iterator) {
  console.log(value);
  if (value === 1) {
    break;
  }
  console.log("This string will not be logged.");
}
// 1

// Another loop using the same iterator
// picks up where the last loop left off.
for (const value of iterator) {
  console.log(value);
}
// 2
// 3

// The iterator is used up.
// This loop will execute no iterations.
for (const value of iterator) {
  console.log(value);
}
// [No output]
```


Generators implement the
[`return()`](../global_objects/generator/return) method, which causes
the generator function to early return when the loop exits. This makes
generators not reusable between loops.

 
 
[js]


```js
function* source() {
  yield 1;
  yield 2;
  yield 3;
}

const generator = source();

for (const value of generator) {
  console.log(value);
  if (value === 1) {
    break;
  }
  console.log("This string will not be logged.");
}
// 1

// The generator is used up.
// This loop will execute no iterations.
for (const value of generator) {
  console.log(value);
}
// [No output]
```




 
### Difference between for\...of and for\...in 

 
Both `for...in` and `for...of` statements iterate over something. The
main difference between them is in what they iterate over.

The [`for...in`](for...in) statement iterates over the [enumerable
string
properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)
of an object, while the `for...of` statement iterates over values that
the [iterable object](../iteration_protocols#the_iterable_protocol)
defines to be iterated over.

The following example shows the difference between a `for...of` loop and
a `for...in` loop when used with an [`Array`](../global_objects/array).

 
 
[js]


```js
Object.prototype.objCustom = function () {};
Array.prototype.arrCustom = function () {};

const iterable = [3, 5, 7];
iterable.foo = "hello";

for (const i in iterable) {
  console.log(i);
}
// "0", "1", "2", "foo", "arrCustom", "objCustom"

for (const i in iterable) {
  if (Object.hasOwn(iterable, i)) {
    console.log(i);
  }
}
// "0" "1" "2" "foo"

for (const i of iterable) {
  console.log(i);
}
// 3 5 7
```


The object `iterable` inherits the properties `objCustom` and
`arrCustom` because it contains both `Object.prototype` and
`Array.prototype` in its [prototype
chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain).

The `for...in` loop logs only [enumerable
properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)
of the `iterable` object. It doesn\'t log array *elements* `3`, `5`, `7`
or `"hello"` because those are not *properties* --- they are *values*.
It logs array *indexes* as well as `arrCustom` and `objCustom`, which
are actual properties. If you\'re not sure why these properties are
iterated over, there\'s a more thorough explanation of how [array
iteration and `for...in`](for...in#array_iteration_and_for...in) work.

The second loop is similar to the first one, but it uses
[`Object.hasOwn()`](../global_objects/object/hasown) to check if the
found enumerable property is the object\'s own, i.e. not inherited. If
it is, the property is logged. Properties `0`, `1`, `2` and `foo` are
logged because they are own properties. Properties `arrCustom` and
`objCustom` are not logged because they are inherited.

The `for...of` loop iterates and logs *values* that `iterable`, as an
array (which is [iterable](../global_objects/array/@@iterator)), defines
to be iterated over. The object\'s *elements* `3`, `5`, `7` are shown,
but none of the object\'s *properties* are.



Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-for-in-and-for-of-statements]](https://tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html#sec-for-in-and-for-of-statements)

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`for...of`

38

12

13Before Firefox 51, using the `for...of` loop construct with the
`const` keyword threw a `SyntaxError` (\"missing = in const
declaration\").

25

7

38

14Before Firefox 51, using the `for...of` loop construct with the
`const` keyword threw a `SyntaxError` (\"missing = in const
declaration\").

25

7

3.0

38

1.0

0.12.0

`async_iterators`

63

12

57

50

7

63

57

46

7

8.0

63

1.0

10.0.0

`closing_iterators`

51

14

53

38

7

51

53

41

7

5.0

51

1.0

6.5.0

 
See also 
--------

 
-   [`Array.prototype.forEach()`](../global_objects/array/foreach)
-   [`Map.prototype.forEach()`](../global_objects/map/foreach)
-   [`Object.entries()`](../global_objects/object/entries)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of>

