Trailing commas
===============

 
**Trailing commas** (sometimes called \"final commas\") can be useful
when adding new elements, parameters, or properties to JavaScript code.
If you want to add a new property, you can add a new line without
modifying the previously last line if that line already uses a trailing
comma. This makes version-control diffs cleaner and editing code might
be less troublesome.

JavaScript has allowed trailing commas in array literals since the
beginning. Trailing commas are now also allowed in object literals,
function parameters, named imports, named exports, and more.

[JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON), however,
disallows all trailing commas.


 
Description
-----------

 
JavaScript allows trailing commas wherever a comma-separated list of
values is accepted and more values may be expected after the last item.
This includes:

-   [Array literals](#arrays)
-   [Object literals](#objects)
-   [Parameter definitions](#parameter_definitions)
-   [Function calls](#function_calls)
-   [Named imports](#named_imports)
-   [Named exports](#named_exports)
-   [Array and object destructuring](#trailing_commas_in_destructuring)

In all these cases, the trailing comma is entirely optional and doesn\'t
change the program\'s semantics in any way.

It is particular useful when adding, removing, or reordering items in a
list that spans multiple lines, because it reduces the number of lines
that need to be changed, which helps with both editing and reviewing the
diff.

 
 
[diff]


```diff
 [
   "foo",
+   "baz",
   "bar",
-   "baz",
 ]
```




 
Examples
--------


 
### Trailing commas in literals 

 
#### Arrays

JavaScript ignores trailing commas in arrays literals:

 
 
[js]


```js
const arr = [
  1,
  2,
  3,
];

arr; // [1, 2, 3]
arr.length; // 3
```


If more than one trailing comma is used, an elision (or hole) is
produced. An array with holes is called
[*sparse*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays)
(a *dense* array has no holes). When iterating arrays for example with
[`Array.prototype.forEach()`](global_objects/array/foreach) or
[`Array.prototype.map()`](global_objects/array/map), array holes are
skipped. Sparse arrays are generally unfavorable, so you should avoid
having multiple trailing commas.

 
 
[js]


```js
const arr = [1, 2, 3, , ,];
arr.length; // 5
```


#### Objects

Trailing commas in object literals are legal as well:

 
 
[js]


```js
const object = {
  foo: "bar",
  baz: "qwerty",
  age: 42,
};
```




 
### Trailing commas in functions 

 
Trailing commas are also allowed in function parameter lists.

#### Parameter definitions 

The following function definition pairs are legal and equivalent to each
other. Trailing commas don\'t affect the
[`length`](global_objects/function/length) property of function
declarations or their [`arguments`](functions/arguments) object.

 
 
[js]


```js
function f(p) {}
function f(p,) {}

(p) => {};
(p,) => {};
```


The trailing comma also works with [method
definitions](functions/method_definitions) for classes or objects:

 
 
[js]


```js
class C {
  one(a,) {}
  two(a, b,) {}
}

const obj = {
  one(a,) {},
  two(a, b,) {},
};
```


#### Function calls 

The following function invocation pairs are legal and equivalent to each
other.

 
 
[js]


```js
f(p);
f(p,);

Math.max(10, 20);
Math.max(10, 20,);
```


#### Illegal trailing commas 

Function parameter definitions or function invocations only containing a
comma will throw a [`SyntaxError`](global_objects/syntaxerror).
Furthermore, when using [rest parameters](functions/rest_parameters),
trailing commas are not allowed:

 
 
[js]


```js
function f(,) {} // SyntaxError: missing formal parameter
(,) => {};       // SyntaxError: expected expression, got ','
f(,)             // SyntaxError: expected expression, got ','

function f(...p,) {} // SyntaxError: parameter after rest parameter
(...p,) => {}        // SyntaxError: expected closing parenthesis, got ','
```




 
### Trailing commas in destructuring 

 
A trailing comma is also allowed on the left-hand side when using
[destructuring assignment](operators/destructuring_assignment):

 
 
[js]


```js
// array destructuring with trailing comma
[a, b,] = [1, 2];

// object destructuring with trailing comma
const o = {
  p: 42,
  q: true,
};
const { p, q, } = o;
```


Again, when using a rest element, a
[`SyntaxError`](global_objects/syntaxerror) will be thrown:

 
 
[js]


```js
const [a, ...b,] = [1, 2, 3];
// SyntaxError: rest element may not have a trailing comma
```




 
### Trailing commas in JSON 

 
As JSON is based on a very restricted subset of JavaScript syntax,
**trailing commas are not allowed in JSON**.

Both lines will throw a `SyntaxError`:

 
 
[js]


```js
JSON.parse("[1, 2, 3, 4, ]");
JSON.parse('{"foo" : 1, }');
// SyntaxError JSON.parse: unexpected character
// at line 1 column 14 of the JSON data
```


Omit the trailing commas to parse the JSON correctly:

 
 
[js]


```js
JSON.parse("[1, 2, 3, 4 ]");
JSON.parse('{"foo" : 1 }');
```




 
### Trailing commas in named imports and named exports 

 
Trailing commas are valid in [named
imports](statements/import#named_import) and [named
exports](statements/export).

#### Named imports 

 
 
[js]


```js
import {
  A,
  B,
  C,
} from "D";

import { X, Y, Z, } from "W";

import { A as B, C as D, E as F, } from "Z";
```


#### Named exports 

 
 
[js]


```js
export {
  A,
  B,
  C,
};

export { A, B, C, };

export { A as B, C as D, E as F, };
```




 
### Quantifier prefix 

 
 
**Note:** The trailing comma in a
[quantifier](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions/Quantifiers)
actually changes its semantics from matching \"exactly `n`\" to matching
\"at least `n`\".


 
 
[js]


```js
/x{2}/; // Exactly 2 occurrences of "x"; equivalent to /xx/
/x{2,}/; // At least 2 occurrences of "x"; equivalent to /xx+/
/x{2,4}/; // 2 to 4 occurrences of "x"; equivalent to /xxx?x?/
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# prod-Elision]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#prod-Elision)

  [ECMAScript Language Specification\
  [\# prod-ObjectLiteral]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#prod-ObjectLiteral)

  [ECMAScript Language Specification\
  [\# prod-ArrayLiteral]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#prod-ArrayLiteral)

  [ECMAScript Language Specification\
  [\# prod-Arguments]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#prod-Arguments)

  [ECMAScript Language Specification\
  [\# prod-FormalParameters]](https://tc39.es/ecma262/multipage/ecmascript-language-functions-and-classes.html#prod-FormalParameters)

  [ECMAScript Language Specification\
  [\#
  prod-CoverParenthesizedExpressionAndArrowParameterList]](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#prod-CoverParenthesizedExpressionAndArrowParameterList)

  [ECMAScript Language Specification\
  [\# prod-NamedImports]](https://tc39.es/ecma262/multipage/ecmascript-language-scripts-and-modules.html#prod-NamedImports)

  [ECMAScript Language Specification\
  [\# prod-NamedExports]](https://tc39.es/ecma262/multipage/ecmascript-language-scripts-and-modules.html#prod-NamedExports)

  [ECMAScript Language Specification\
  [\# prod-QuantifierPrefix]](https://tc39.es/ecma262/multipage/text-processing.html#prod-QuantifierPrefix)

  [ECMAScript Language Specification\
  [\# prod-annexB-InvalidBracedQuantifier]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#prod-annexB-InvalidBracedQuantifier)
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`Trailing_commas`

1

12

1

9.5

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`trailing_commas_in_dynamic_import`

91

91

No

No

15

91

No

No

15

16.0

91

1.17

17.5.016.15.0--17.0.0

16.14.0--16.15.0The second parameter no longer throws a parser error,
but the `--experimental-json-modules` flag is still needed to load JSON
modules.

`trailing_commas_in_functions`

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

`trailing_commas_in_object_literals`

1

12

1

9.5

3

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

 
-   [Grammar and
    types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types)
    guide



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Trailing_commas>

