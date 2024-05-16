ReferenceError: \"x\" is not defined
====================================

 
The JavaScript exception \"*variable* is not defined\" occurs when there
is a non-existent variable referenced somewhere.


 
Message
-------

 
```text
ReferenceError: "x" is not defined (V8-based & Firefox)
ReferenceError: Can't find variable: x (Safari)
```



 
Error type 
----------

 
[`ReferenceError`](../global_objects/referenceerror).



 
What went wrong? 
----------------

 
There is a non-existent variable referenced somewhere. This variable
needs to be declared, or you need to make sure it is available in your
current script or
[scope](https://developer.mozilla.org/en-US/docs/Glossary/Scope).

 
**Note:** When loading a library (such as jQuery), make sure it is
loaded before you access library variables, such as \"\$\". Put the
[`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)
element that loads the library before your code that uses it.




 
Examples
--------


 
### Variable not declared 

 
 
 
[js]


```js
foo.substring(1); // ReferenceError: foo is not defined
```


The \"foo\" variable isn\'t defined anywhere. It needs to be some
string, so that the
[`String.prototype.substring()`](../global_objects/string/substring)
method will work.

 
 
[js]


```js
const foo = "bar";
foo.substring(1); // "ar"
```




 
### Wrong scope 

 
A variable needs to be available in the current context of execution.
Variables defined inside a [function](../functions) cannot be accessed
from anywhere outside the function, because the variable is defined only
in the scope of the function

 
 
[js]


```js
function numbers() {
  const num1 = 2;
  const num2 = 3;
  return num1 + num2;
}

console.log(num1); // ReferenceError num1 is not defined.
```


However, a function can access all variables and functions defined
inside the scope in which it is defined. In other words, a function
defined in the global scope can access all variables defined in the
global scope.

 
 
[js]


```js
const num1 = 2;
const num2 = 3;

function numbers() {
  return num1 + num2;
}

console.log(numbers()); // 5
```




 
See also 
--------

 
-   [Scope](https://developer.mozilla.org/en-US/docs/Glossary/Scope)
-   [Declaring variables in the JavaScript
    Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#declaring_variables)
-   [Function scope in the JavaScript
    Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_scope)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Not_defined>

