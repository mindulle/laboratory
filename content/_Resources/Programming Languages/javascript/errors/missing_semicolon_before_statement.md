SyntaxError: missing ; before statement
=======================================

 
The JavaScript exception \"missing ; before statement\" occurs when
there is a semicolon (`;`) missing somewhere and can\'t be added by
[automatic semicolon insertion
(ASI)](../lexical_grammar#automatic_semicolon_insertion). You need to
provide a semicolon, so that JavaScript can parse the source code
correctly.


 
Message
-------

 
```text
SyntaxError: Expected ';' (Edge)
SyntaxError: missing ; before statement (Firefox)
```



 
Error type 
----------

 
[`SyntaxError`](../global_objects/syntaxerror).



 
What went wrong? 
----------------

 
There is a semicolon (`;`) missing somewhere. [JavaScript
statements](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements)
must be terminated with semicolons. Some of them are affected by
[automatic semicolon insertion
(ASI)](../lexical_grammar#automatic_semicolon_insertion), but in this
case you need to provide a semicolon, so that JavaScript can parse the
source code correctly.

However, oftentimes, this error is only a consequence of another error,
like not escaping strings properly, or using `var` wrongly. You might
also have too many parenthesis somewhere. Carefully check the syntax
when this error is thrown.



 
Examples
--------


 
### Unescaped strings 

 
This error can occur easily when not escaping strings properly and the
JavaScript engine is expecting the end of your string already. For
example:

 
 
[js]


```js
const foo = 'Tom's bar';
// SyntaxError: missing ; before statement
```


You can use double quotes, or escape the apostrophe:

 
 
[js]


```js
const foo = "Tom's bar";
// OR
const foo = 'Tom\'s bar';
```




 
### Declaring properties with keyword 

 
You **cannot** declare properties of an object or array with a `let`,
`const`, or `var` declaration.

 
 
[js]


```js
const obj = {};
const obj.foo = "hi"; // SyntaxError missing ; before statement

const array = [];
const array[0] = "there"; // SyntaxError missing ; before statement
```


Instead, omit the keyword:

 
 
[js]


```js
const obj = {};
obj.foo = "hi";

const array = [];
array[0] = "there";
```




 
### Bad keywords 

 
If you come from another programming language, it is also common to use
keywords that don\'t mean the same or have no meaning at all in
JavaScript:

 
 
[js]


```js
def print(info) {
  console.log(info);
} // SyntaxError missing ; before statement
```


Instead, use `function` instead of `def`:

 
 
[js]


```js
function print(info) {
  console.log(info);
}
```




 
See also 
--------

 
-   [Automatic semicolon insertion
    (ASI)](../lexical_grammar#automatic_semicolon_insertion)
-   [Statements and
    declarations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_semicolon_before_statement>

