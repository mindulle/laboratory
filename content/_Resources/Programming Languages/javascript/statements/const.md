const
=====

 
The `const` declaration declares block-scoped local variables. The value
of a constant can\'t be changed through reassignment using the
[assignment operator](../operators/assignment), but if a constant is an
[object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#objects),
its properties can be added, updated, or removed.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
const name1 = value1;
const name1 = value1, name2 = value2;
const name1 = value1, name2 = value2, /* …, */ nameN = valueN;
```


[`nameN`](#namen)

:   The name of the variable to declare. Each must be a legal JavaScript
    [identifier](../lexical_grammar#identifiers) or a [destructuring
    binding pattern](../operators/destructuring_assignment).

[`valueN`](#valuen)

:   Initial value of the variable. It can be any legal expression.



 
Description
-----------

 
The `const` declaration is very similar to [`let`](let):

-   `const` declarations are scoped to blocks as well as functions.
-   `const` declarations can only be accessed after the place of
    declaration is reached (see [temporal dead
    zone](let#temporal_dead_zone_tdz)). For this reason, `const`
    declarations are commonly regarded as
    [non-hoisted](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting).
-   `const` declarations do not create properties on
    [`globalThis`](../global_objects/globalthis) when declared at the
    top level of a script.
-   `const` declarations cannot be [redeclared](let#redeclarations) by
    any other declaration in the same scope.
-   `const` begins [*declarations*, not
    *statements*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements#difference_between_statements_and_declarations).
    That means you cannot use a lone `const` declaration as the body of
    a block (which makes sense, since there\'s no way to access the
    variable).
     
     
    [js]
    

    ```js
    if (true) const a = 1; // SyntaxError: Lexical declaration cannot appear in a single-statement context
    ```
    

An initializer for a constant is required. You must specify its value in
the same declaration. (This makes sense, given that it can\'t be changed
later.)

 
 
[js]


```js
const FOO; // SyntaxError: Missing initializer in const declaration
```


The `const` declaration creates an immutable reference to a value. It
does *not* mean the value it holds is immutable --- just that the
variable identifier cannot be reassigned. For instance, in the case
where the content is an object, this means the object\'s contents (e.g.,
its properties) can be altered. You should understand `const`
declarations as \"create a variable whose *identity* remains constant\",
not \"whose *value* remains constant\" --- or, \"create immutable
[bindings](https://developer.mozilla.org/en-US/docs/Glossary/Binding)\",
not \"immutable values\".

Many style guides (including
[MDN\'s](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Writing_style_guide/Code_style_guide/JavaScript#variable_declarations))
recommend using `const` over [`let`](let) whenever a variable is not
reassigned in its scope. This makes the intent clear that a variable\'s
type (or value, in the case of a primitive) can never change. Others may
prefer `let` for non-primitives that are mutated.

The list that follows the `const` keyword is called a
*[binding](https://developer.mozilla.org/en-US/docs/Glossary/Binding)
list* and is separated by commas, where the commas are *not* [comma
operators](../operators/comma_operator) and the `=` signs are *not*
[assignment operators](../operators/assignment). Initializers of later
variables can refer to earlier variables in the list.



 
Examples
--------


 
### Basic const usage 

 
Constants can be declared with uppercase or lowercase, but a common
convention is to use all-uppercase letters, especially for primitives
because they are truly immutable.

 
 
[js]


```js
// define MY_FAV as a constant and give it the value 7
const MY_FAV = 7;

console.log("my favorite number is: " + MY_FAV);
```


 
 
[js]


```js
// Re-assigning to a constant variable throws an error
MY_FAV = 20; // TypeError: Assignment to constant variable

// Redeclaring a constant throws an error
const MY_FAV = 20; // SyntaxError: Identifier 'MY_FAV' has already been declared
var MY_FAV = 20; // SyntaxError: Identifier 'MY_FAV' has already been declared
let MY_FAV = 20; // SyntaxError: Identifier 'MY_FAV' has already been declared
```




 
### Block scoping 

 
It\'s important to note the nature of block scoping.

 
 
[js]


```js
const MY_FAV = 7;

if (MY_FAV === 7) {
  // This is fine because it's in a new block scope
  const MY_FAV = 20;
  console.log(MY_FAV); // 20

  // var declarations are not scoped to blocks so this throws an error
  var MY_FAV = 20; // SyntaxError: Identifier 'MY_FAV' has already been declared
}

console.log(MY_FAV); // 7
```




 
### const in objects and arrays 

 
`const` also works on objects and arrays. Attempting to overwrite the
object throws an error \"Assignment to constant variable\".

 
 
[js]


```js
const MY_OBJECT = { key: "value" };
MY_OBJECT = { OTHER_KEY: "value" };
```


However, object keys are not protected, so the following statement is
executed without problem.

 
 
[js]


```js
MY_OBJECT.key = "otherValue";
```


You would need to use
[`Object.freeze()`](../global_objects/object/freeze) to make an object
immutable.

The same applies to arrays. Assigning a new array to the variable throws
an error \"Assignment to constant variable\".

 
 
[js]


```js
const MY_ARRAY = [];
MY_ARRAY = ["B"];
```


Still, it\'s possible to push items into the array and thus mutate it.

 
 
[js]


```js
MY_ARRAY.push("A"); // ["A"]
```




 
### Declaration with destructuring 

 
The left-hand side of each `=` can also be a binding pattern. This
allows creating multiple variables at once.

 
 
[js]


```js
const result = /(a+)(b+)(c+)/.exec("aaabcc");
const [, a, b, c] = result;
console.log(a, b, c); // "aaa" "b" "cc"
```


For more information, see [Destructuring
assignment](../operators/destructuring_assignment).



Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-let-and-const-declarations]](https://tc39.es/ecma262/multipage/ecmascript-language-statements-and-declarations.html#sec-let-and-const-declarations)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`const`

21

12

36\[\"Before Firefox 13, `const` is implemented, but re-assignment is
not failing.\", \"Before Firefox 46, a `TypeError` was thrown on
redeclaration instead of a `SyntaxError`.\"\]

9

5.1

25

36\[\"Before Firefox 13, `const` is implemented, but re-assignment is
not failing.\", \"Before Firefox 46, a `TypeError` was thrown on
redeclaration instead of a `SyntaxError`.\"\]

10.1

5

1.5

4.4

1.0

6.0.0

 
See also 
--------

 
-   [`var`](var)
-   [`let`](let)
-   [Constants in the JavaScript
    Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#constants)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const>

