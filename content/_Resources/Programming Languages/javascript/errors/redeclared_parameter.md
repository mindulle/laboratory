SyntaxError: redeclaration of formal parameter \"x\"
====================================================

 
The JavaScript exception \"redeclaration of formal parameter\" occurs
when the same variable name occurs as a function parameter and is then
redeclared using a [`let`](../statements/let) assignment in a function
body again.


 
Message
-------

 
```text
SyntaxError: Identifier "x" has already been declared (V8-based)
SyntaxError: redeclaration of formal parameter "x" (Firefox)
SyntaxError: Cannot declare a let variable twice: 'x'. (Safari)
```



 
Error type 
----------

 
[`SyntaxError`](../global_objects/syntaxerror)



 
What went wrong? 
----------------

 
The same variable name occurs as a function parameter and is then
redeclared using a [`let`](../statements/let) assignment in a function
body again. Redeclaring the same variable within the same function or
block scope using `let` is not allowed in JavaScript.



 
Examples
--------


 
### Redeclared argument 

 
In this case, the variable \"arg\" redeclares the argument.

 
 
[js]


```js
function f(arg) {
  let arg = "foo";
}

// SyntaxError: redeclaration of formal parameter "arg"
```


If you want to change the value of \"arg\" in the function body, you can
do so, but you do not need to declare the same variable again. In other
words: you can omit the `let` keyword. If you want to create a new
variable, you need to rename it as conflicts with the function parameter
already.

 
 
[js]


```js
function f(arg) {
  arg = "foo";
}

function g(arg) {
  let bar = "foo";
}
```




 
See also 
--------

 
-   [`let`](../statements/let)
-   [`const`](../statements/const)
-   [`var`](../statements/var)
-   [Grammar and
    types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types)
    guide



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Redeclared_parameter>

