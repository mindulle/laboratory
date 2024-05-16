ReferenceError: assignment to undeclared variable \"x\"
=======================================================

 
The JavaScript [strict mode](../strict_mode)-only exception \"Assignment
to undeclared variable\" occurs when the value has been assigned to an
undeclared variable.


 
Message
-------

 
```text
ReferenceError: x is not defined (V8-based)
ReferenceError: assignment to undeclared variable x (Firefox)
ReferenceError: Can't find variable: x (Safari)
```



 
Error type 
----------

 
[`ReferenceError`](../global_objects/referenceerror) in [strict
mode](../strict_mode) only.



 
What went wrong? 
----------------

 
A value has been assigned to an undeclared variable. In other words,
there was an assignment without the `var` keyword. There are some
differences between declared and undeclared variables, which might lead
to unexpected results and that\'s why JavaScript presents an error in
strict mode.

Three things to note about declared and undeclared variables:

-   Declared variables are constrained in the execution context in which
    they are declared. Undeclared variables are always global.
-   Declared variables are created before any code is executed.
    Undeclared variables do not exist until the code assigning to them
    is executed.
-   Declared variables are a non-configurable property of their
    execution context (function or global). Undeclared variables are
    configurable (e.g. can be deleted).

For more details and examples, see the [`var`](../statements/var)
reference page.

Errors about undeclared variable assignments occur in [strict mode
code](../strict_mode) only. In non-strict code, they are silently
ignored.



 
Examples
--------


 
### Invalid cases 

 
In this case, the variable \"bar\" is an undeclared variable.

 
 
[js]


```js
function foo() {
  "use strict";
  bar = true;
}
foo(); // ReferenceError: assignment to undeclared variable bar
```




 
### Valid cases 

 
To make \"bar\" a declared variable, you can add a
[`let`](../statements/let), [`const`](../statements/var), or
[`var`](../statements/var) keyword in front of it.

 
 
[js]


```js
function foo() {
  "use strict";
  const bar = true;
}
foo();
```




 
See also 
--------

 
-   [Strict mode](../strict_mode)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Undeclared_var>

