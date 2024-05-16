Expression statement
====================

 
An **expression statement** is an expression used in a place where a
statement is expected. The expression is evaluated and its result is
discarded --- therefore, it makes sense only for expressions that have
side effects, such as executing a function or updating a variable.


 
Syntax
------

 
 
 
[js]


```js
expression;
```


[`expression`](#expression)

:   An arbitrary
    [expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators)
    to be evaluated. There are [certain
    expressions](#forbidden_expressions) that may be ambiguous with
    other statements and are thus forbidden.



 
Description
-----------

 
Apart from the [dedicated statement
syntaxes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements),
you can also use almost any
[expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators)
as a statement on its own. The expression statement syntax requires a
semicolon at the end, but the [automatic semicolon
insertion](../lexical_grammar#automatic_semicolon_insertion) process may
insert one for you if the lack of a semicolon results in invalid syntax.

Because the expression is evaluated and then discarded, the result of
the expression is not available. Therefore, the expression must have
some side effect for it to be useful. Expression statements are
commonly:

-   Function calls (`console.log("Hello");`,
    `[1, 2, 3].forEach((i) => console.log(i));`)
-   [Tagged template literals](../template_literals#tagged_templates)
-   [Assignment
    expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#assignment_operators),
    including compound assignments
-   [Increment and decrement
    operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#increment_and_decrement)
-   [`delete`](../operators/delete)
-   [`import()`](../operators/import)
-   [`yield`](../operators/yield) and [`yield*`](../operators/yield*)

Others may also have side effects if they invoke
[getters](../functions/get) or trigger [type
coercions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#type_coercion).



 
### Forbidden expressions 

 
In order for an expression to be used as a statement, it must not be
ambiguous with other statement syntaxes. Therefore, the expression must
not start with any of the following tokens:

-   `function`: which would be a [`function` declaration](function) or
    [`function*` declaration](function*), not a [`function`
    expression](../operators/function) or [`function*`
    expression](../operators/function*)
-   `async function`: which would be an [`async function`
    declaration](async_function) or [`async function*`
    declaration](async_function*), not an [`async function`
    expression](../operators/async_function) or [`async function*`
    expression](../operators/async_function*)
-   `class`: which would be a [`class` declaration](class), not a
    [`class` expression](../operators/class)
-   `let[`: which would be a [`let` declaration](let) with [array
    destructuring](../operators/destructuring_assignment), not a
    [property accessor](../operators/property_accessors) on a variable
    called `let` (`let` can only be an identifier in [non-strict
    mode](../strict_mode#extra_reserved_words))
-   `{`: which would be a [block statement](block), not an [object
    literal](../operators/object_initializer)

Therefore, all of the following are invalid:

 
 
[js]


```js
function foo() {
  console.log("foo");
}(); // SyntaxError: Unexpected token '('

// For some reason, you have a variable called `let`
var let = [1, 2, 3];
let[0] = 4; // SyntaxError: Invalid destructuring assignment target

{
  foo: 1,
  bar: 2, // SyntaxError: Unexpected token ':'
};
```


More dangerously, sometimes the code happens to be valid syntax, but is
not what you intend.

 
 
[js]


```js
// For some reason, you have a variable called `let`
var let = [1, 2, 3];

function setIndex(index, value) {
  if (index >= 0) {
    // Intend to assign to the array `let`, but instead creates an extra variable!
    let[index] = value;
  }
}

setIndex(0, [1, 2]);
console.log(let); // [1, 2, 3]

// This is not an object literal, but a block statement,
// where `foo` is a label and `1` is an expression statement.
// This often happens in the console
{ foo: 1 };
```


To avoid these problems, you can use parentheses, so that the statement
is unambiguously an expression statement.

 
 
[js]


```js
(function foo() {
  console.log("foo");
})();
```




 
Examples
--------


 
### Avoiding control flow statements 

 
You can avoid almost all use of control flow statements using expression
statements. For example, `if...else` can be replaced with [ternary
operators](../operators/conditional_operator) and [logical
operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#binary_logical_operators).
Iterative statements like `for` or `for...of` can be replaced with
[array methods](../global_objects/array#instance_methods).

 
 
[js]


```js
// Using control flow statements
function range(start, end) {
  if (start > end) {
    [start, end] = [end, start];
  }
  const result = [];
  for (let i = start; i < end; i++) {
    result.push(i);
  }
  return result;
}

// Using expression statements
function range2(start, end) {
  start > end && ([start, end] = [end, start]);
  return Array.from({ length: end - start }, (_, i) => start + i);
}
```


 
**Warning:** This only demonstrates a capability of the language.
Excessive use of expression statements as a substitute for control-flow
statements can make code much less readable.




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-expression-statement]](https://tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html#sec-expression-statement)

  -----------------------------------------------------------------------------------------------------------------------------------------------------


 
See also 
--------

 
-   [Statements and
    declarations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements)
-   [Expressions and
    operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/Expression_statement>

