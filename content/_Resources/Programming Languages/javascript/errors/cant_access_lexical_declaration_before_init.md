ReferenceError: can\'t access lexical declaration \'X\' before initialization
=============================================================================


The JavaScript exception \"can\'t access lexical declaration
\`*variable*\' before initialization\" occurs when a lexical variable
was accessed before it was initialized. This happens within any block
statement, when [`let`](../statements/let) or
[`const`](../statements/const) variables are accessed before the place
where they are declared is executed.



Message
-------


```text
ReferenceError: Cannot access 'X' before initialization (V8-based)
ReferenceError: can't access lexical declaration 'X' before initialization (Firefox)
ReferenceError: Cannot access uninitialized variable. (Safari)
```




Error type 
----------


[`ReferenceError`](../global_objects/referenceerror)




What went wrong? 
----------------


A lexical variable was accessed before it was initialized. This happens
within any block statement, when variables declared with
[`let`](../statements/let) or [`const`](../statements/const) are
accessed before the place where they are declared has been executed.

Note that it is the execution order of access and variable declaration
that matters, not the order in which the statements appear in the code.
For more information, see the description of [Temporal Dead
Zone](../statements/let#temporal_dead_zone_tdz).

This issue does not occur for variables declared using `var`, because
they are initialized with a default value of `undefined` when they are
[hoisted](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting).

This error can also occur in [cyclic
imports](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules#cyclic_imports)
when a module uses a variable that depends on the module itself being
evaluated.




Examples
--------



### Invalid cases 


In this case, the variable `foo` is accessed before it is declared. At
this point foo has not been initialized with a value, so accessing the
variable throws a reference error.



[js]


```js
function test() {
  // Accessing the 'const' variable foo before it's declared
  console.log(foo); // ReferenceError: foo is not initialized
  const foo = 33; // 'foo' is declared and initialized here using the 'const' keyword
}

test();
```


In this example, the imported variable `a` is accessed but is
uninitialized, because the evaluation of `a.js` is blocked by the
evaluation of the current module `b.js`.



[js]


```js
// -- a.js (entry module) --
import { b } from "./b.js";

export const a = 2;

// -- b.js --
import { a } from "./a.js";

console.log(a); // ReferenceError: Cannot access 'a' before initialization
export const b = 1;
```





### Valid cases 


In the following example, we correctly declare a variable using the
`const` keyword before accessing it.



[js]


```js
function test() {
  // Declaring variable foo
  const foo = 33;
  console.log(foo); // 33
}
test();
```


In this example, the imported variable `a` is asynchronously accessed,
so both modules are evaluated before the access to `a` occurs.



[js]


```js
// -- a.js (entry module) --
import { b } from "./b.js";

export const a = 2;

// -- b.js --
import { a } from "./a.js";

setTimeout(() => {
  console.log(a); // 2
}, 10);
export const b = 1;
```





See also 
--------


-   [`let`](../statements/let)
-   [`const`](../statements/const)
-   [`var`](../statements/var)
-   [`class`](../statements/class)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_access_lexical_declaration_before_init>

