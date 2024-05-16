SyntaxError: missing variable name
==================================

 
The JavaScript exception \"missing variable name\" is a common error. It
is usually caused by omitting a variable name or a typographic error.


 
Message
-------

 
```text
SyntaxError: missing variable name (Firefox)
SyntaxError: Unexpected token '='. Expected a parameter pattern or a ')' in parameter list. (Safari)
```



 
Error type 
----------

 
[`SyntaxError`](../global_objects/syntaxerror)



 
What went wrong? 
----------------

 
A variable is missing a name. The cause is most likely a typo or a
forgotten variable name. Make sure that you\'ve provided the name of the
variable before the `=` sign.

When declaring multiple variables at the same time, make sure that the
previous lines/declaration does not end with a comma instead of a
semicolon.



 
Examples
--------


 
### Missing a variable name 

 
 
 
[js]


```js
const = "foo";
```


It is easy to forget to assign a name for your variable!

 
 
[js]


```js
const description = "foo";
```




 
### Reserved keywords can\'t be variable names 

 
There are a few variable names that are [reserved
keywords](../lexical_grammar#keywords). You can\'t use these. Sorry :(

 
 
[js]


```js
const debugger = "whoop";
// SyntaxError: missing variable name
```




 
### Declaring multiple variables 

 
Pay special attention to commas when declaring multiple variables. Is
there an excess comma, or did you use commas instead of semicolons? Did
you remember to assign values for all your `const` variables?

 
 
[js]


```js
let x, y = "foo",
const z, = "foo"

const first = document.getElementById("one"),
const second = document.getElementById("two"),

// SyntaxError: missing variable name
```


The fixed version:

 
 
[js]


```js
let x,
  y = "foo";
const z = "foo";

const first = document.getElementById("one");
const second = document.getElementById("two");
```




 
### Arrays

 
[`Array`](../global_objects/array) literals in JavaScript need square
brackets around the values. This won\'t work:

 
 
[js]


```js
const arr = 1,2,3,4,5;
// SyntaxError: missing variable name
```


This would be correct:

 
 
[js]


```js
const arr = [1, 2, 3, 4, 5];
```




 
See also 
--------

 
-   [Lexical grammar](../lexical_grammar)
-   [`var`](../statements/var)
-   [Grammar and
    types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types)
    guide



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/No_variable_name>

