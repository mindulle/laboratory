undefined
=========

 
The `undefined` global property represents the primitive value
[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#undefined_type).
It is one of JavaScript\'s [primitive
types](https://developer.mozilla.org/en-US/docs/Glossary/Primitive).


 
Try it 
------

 



 
Value
-----

 
The primitive value
[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#undefined_type).

 
Property attributes of `undefined`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
`undefined` is a property of the *global object*. That is, it is a
variable in global scope.

In all non-legacy browsers, `undefined` is a non-configurable,
non-writable property. Even when this is not the case, avoid overriding
it.

A variable that has not been assigned a value is of type `undefined`. A
method or statement also returns `undefined` if the variable that is
being evaluated does not have an assigned value. A function returns
`undefined` if a value was not [`returned`](../statements/return).

 
**Note:** While you can use `undefined` as an
[identifier](https://developer.mozilla.org/en-US/docs/Glossary/Identifier)
(variable name) in any scope other than the global scope (because
`undefined` is not a [reserved
word](../lexical_grammar#reserved_words)), doing so is a very bad idea
that will make your code difficult to maintain and debug.

 
 
[js]


```js
// DON'T DO THIS

(() => {
  const undefined = "foo";
  console.log(undefined, typeof undefined); // foo string
})();

((undefined) => {
  console.log(undefined, typeof undefined); // foo string
})("foo");
```





 
Examples
--------


 
### Strict equality and undefined 

 
You can use `undefined` and the strict equality and inequality operators
to determine whether a variable has a value. In the following code, the
variable `x` is not initialized, and the `if` statement evaluates to
true.

 
 
[js]


```js
let x;
if (x === undefined) {
  // these statements execute
} else {
  // these statements do not execute
}
```


 
**Note:** The *strict equality* operator (as opposed to the *standard
equality* operator) must be used here, because `x == undefined` also
checks whether `x` is `null`, while strict equality doesn\'t. This is
because `null` is not equivalent to `undefined`.

See [Equality comparison and
sameness](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness)
for details.




 
### typeof operator and undefined 

 
Alternatively, [`typeof`](../operators/typeof) can be used:

 
 
[js]


```js
let x;
if (typeof x === "undefined") {
  // these statements execute
}
```


One reason to use [`typeof`](../operators/typeof) is that it does not
throw an error if the variable has not been declared.

 
 
[js]


```js
// x has not been declared before
// evaluates to true without errors
if (typeof x === "undefined") {
  // these statements execute
}

// Throws a ReferenceError
if (x === undefined) {
}
```


However, there is another alternative. JavaScript is a statically scoped
language, so knowing if a variable is declared can be read by seeing
whether it is declared in an enclosing context.

The global scope is bound to the [global object](globalthis), so
checking the existence of a variable in the global context can be done
by checking the existence of a property on the *global object*, using
the [`in`](../operators/in) operator, for instance:

 
 
[js]


```js
if ("x" in window) {
  // These statements execute only if x is defined globally
}
```




 
### void operator and undefined 

 
The [`void`](../operators/void) operator is a third alternative.

 
 
[js]


```js
let x;
if (x === void 0) {
  // these statements execute
}

// y has not been declared before
if (y === void 0) {
  // throws Uncaught ReferenceError: y is not defined
}
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-undefined]](https://tc39.es/ecma262/multipage/global-object.html#sec-undefined)

  ---------------------------------------------------------------------------------------------


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

`undefined`

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

 
-   [JavaScript data types and data
    structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
-   [`null`](../operators/null)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined>

