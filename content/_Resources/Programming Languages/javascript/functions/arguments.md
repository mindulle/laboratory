The arguments object
====================


`arguments` is an array-like object accessible inside
[functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
that contains the values of the arguments passed to that function.



Try it 
------






Description
-----------


 
**Note:** In modern code, [rest parameters](rest_parameters) should be
preferred.


The `arguments` object is a local variable available within all
non-[arrow](arrow_functions) functions. You can refer to a function\'s
arguments inside that function by using its `arguments` object. It has
entries for each argument the function was called with, with the first
entry\'s index at `0`.

For example, if a function is passed 3 arguments, you can access them as
follows:



[js]


```js
arguments[0]; // first argument
arguments[1]; // second argument
arguments[2]; // third argument
```


The `arguments` object is useful for functions called with more
arguments than they are formally declared to accept, called [*variadic
functions*](https://en.wikipedia.org/wiki/Variadic_function), such as
[`Math.min()`](../global_objects/math/min). This example function
accepts any number of string arguments and returns the longest one:



[js]


```js
function longestString() {
  let longest = "";
  for (let i = 0; i < arguments.length; i++) {
    if (arguments[i].length > longest.length) {
      longest = arguments[i];
    }
  }
  return longest;
}
```


You can use [`arguments.length`](arguments/length) to count how many
arguments the function was called with. If you instead want to count how
many parameters a function is declared to accept, inspect that
function\'s [`length`](../global_objects/function/length) property.




### Assigning to indices 


Each argument index can also be set or reassigned:



[js]


```js
arguments[1] = "new value";
```


Non-strict functions that only have simple parameters (that is, no rest,
default, or destructured parameters) will sync the new value of
parameters with the `arguments` object, and vice versa:



[js]


```js
function func(a) {
  arguments[0] = 99; // updating arguments[0] also updates a
  console.log(a);
}
func(10); // 99

function func2(a) {
  a = 99; // updating a also updates arguments[0]
  console.log(arguments[0]);
}
func2(10); // 99
```


Non-strict functions that *are* passed [rest](rest_parameters),
[default](default_parameters), or
[destructured](../operators/destructuring_assignment) parameters will
not sync new values assigned to parameters in the function body with the
`arguments` object. Instead, the `arguments` object in non-strict
functions with complex parameters will always reflect the values passed
to the function when the function was called.



[js]


```js
function funcWithDefault(a = 55) {
  arguments[0] = 99; // updating arguments[0] does not also update a
  console.log(a);
}
funcWithDefault(10); // 10

function funcWithDefault2(a = 55) {
  a = 99; // updating a does not also update arguments[0]
  console.log(arguments[0]);
}
funcWithDefault2(10); // 10

// An untracked default parameter
function funcWithDefault3(a = 55) {
  console.log(arguments[0]);
  console.log(arguments.length);
}
funcWithDefault3(); // undefined; 0
```


This is the same behavior exhibited by all [strict-mode
functions](../strict_mode#making_eval_and_arguments_simpler), regardless
of the type of parameters they are passed. That is, assigning new values
to parameters in the body of the function never affects the `arguments`
object, nor will assigning new values to the `arguments` indices affect
the value of parameters, even when the function only has simple
parameters.

 
**Note:** You cannot write a `"use strict";` directive in the body of a
function definition that accepts rest, default, or destructured
parameters. Doing so will throw [a syntax
error](../errors/strict_non_simple_params).





### arguments is an array-like object 


`arguments` is an array-like object, which means that `arguments` has a
[`length`](arguments/length) property and properties indexed from zero,
but it doesn\'t have [`Array`](../global_objects/array)\'s built-in
methods like [`forEach()`](../global_objects/array/foreach) or
[`map()`](../global_objects/array/map). However, it can be converted to
a real `Array`, using one of [`slice()`](../global_objects/array/slice),
[`Array.from()`](../global_objects/array/from), or [spread
syntax](../operators/spread_syntax).



[js]


```js
const args = Array.prototype.slice.call(arguments);
// or
const args = Array.from(arguments);
// or
const args = [...arguments];
```


For common use cases, using it as an array-like object is sufficient,
since it both [is iterable](arguments/@@iterator) and has `length` and
number indices. For example,
[`Function.prototype.apply()`](../global_objects/function/apply) accepts
array-like objects.



[js]


```js
function midpoint() {
  return (
    (Math.min.apply(null, arguments) + Math.max.apply(null, arguments)) / 2
  );
}

console.log(midpoint(3, 1, 4, 1, 5)); // 3
```





Properties
----------



[`arguments.callee`](arguments/callee) [Deprecated]

:   Reference to the currently executing function that the arguments
    belong to. Forbidden in strict mode.

[`arguments.length`](arguments/length)

:   The number of arguments that were passed to the function.

[`arguments[@@iterator]`](arguments/@@iterator)

:   Returns a new [Array iterator](../global_objects/array/@@iterator)
    object that contains the values for each index in `arguments`.




Examples
--------



### Defining a function that concatenates several strings 


This example defines a function that concatenates several strings. The
function\'s only formal argument is a string containing the characters
that separate the items to concatenate.



[js]


```js
function myConcat(separator) {
  const args = Array.prototype.slice.call(arguments, 1);
  return args.join(separator);
}
```


You can pass as many arguments as you like to this function. It returns
a string list using each argument in the list:



[js]


```js
myConcat(", ", "red", "orange", "blue");
// "red, orange, blue"

myConcat("; ", "elephant", "giraffe", "lion", "cheetah");
// "elephant; giraffe; lion; cheetah"

myConcat(". ", "sage", "basil", "oregano", "pepper", "parsley");
// "sage. basil. oregano. pepper. parsley"
```





### Defining a function that creates HTML lists 


This example defines a function that creates a string containing HTML
for a list. The only formal argument for the function is a string that
is `"u"` if the list is to be [unordered
(bulleted)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul),
or `"o"` if the list is to be [ordered
(numbered)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol).
The function is defined as follows:



[js]


```js
function list(type) {
  let html = `<${type}l><li>`;
  const args = Array.prototype.slice.call(arguments, 1);
  html += args.join("</li><li>");
  html += `</li></${type}l>`; // end list
  return html;
}
```


You can pass any number of arguments to this function, and it adds each
argument as a list item to a list of the type indicated. For example:



[js]


```js
list("u", "One", "Two", "Three");
// "<ul><li>One</li><li>Two</li><li>Three</li></ul>"
```





### Using typeof with arguments 


The [`typeof`](../operators/typeof) operator returns `'object'` when
used with `arguments`



[js]


```js
console.log(typeof arguments); // 'object'
```


The type of individual arguments can be determined by indexing
`arguments`:



[js]


```js
console.log(typeof arguments[0]); // returns the type of the first argument
```




Specifications
--------------


  ----------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-arguments-exotic-objects]](https://tc39.es/ecma262/multipage/ordinary-and-exotic-objects-behaviours.html#sec-arguments-exotic-objects)

  ----------------------------------------------------------------------------------------------------------------------------------------------------


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

`@@iterator`

52

12

46

39

9

52

46

41

9

6.0

52

1.0

4.0.0

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

`callee`

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

`length`

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


See also 
--------


-   [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
    guide
-   [Functions](../functions)
-   [Rest parameters](rest_parameters)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments>

