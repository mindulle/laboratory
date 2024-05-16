SyntaxError: \"x\" is a reserved identifier
===========================================

 
The JavaScript exception \"*variable* is a reserved identifier\" occurs
when [reserved keywords](../lexical_grammar#keywords) are used as
identifiers.


 
Message
-------

 
```text
SyntaxError: Unexpected reserved word (V8-based)
SyntaxError: implements is a reserved identifier (Firefox)
SyntaxError: Cannot use the reserved word 'implements' as a variable name. (Safari)
```



 
Error type 
----------

 
[`SyntaxError`](../global_objects/syntaxerror)



 
What went wrong? 
----------------

 
[Reserved keywords](../lexical_grammar#keywords) will throw in if they
are used as identifiers. These are reserved in strict mode and sloppy
mode:

-   `enum`

The following are only reserved when they are found in strict mode code:

-   `implements`
-   `interface`
-   [`let`](../statements/let)
-   `package`
-   `private`
-   `protected`
-   `public`
-   `static`



 
Examples
--------


 
### Strict and non-strict reserved keywords 

 
The `enum` identifier is generally reserved.

 
 
[js]


```js
const enum = { RED: 0, GREEN: 1, BLUE: 2 };
// SyntaxError: enum is a reserved identifier
```


In strict mode code, more identifiers are reserved.

 
 
[js]


```js
"use strict";
const package = ["potatoes", "rice", "fries"];
// SyntaxError: package is a reserved identifier
```


You\'ll need to rename these variables.

 
 
[js]


```js
const colorEnum = { RED: 0, GREEN: 1, BLUE: 2 };
const list = ["potatoes", "rice", "fries"];
```




 
### Update older browsers 

 
If you are using an older browser that does not yet implement
[`let`](../statements/let) or [`class`](../statements/class), for
example, you should update to a more recent browser version that does
support these new language features.

 
 
[js]


```js
"use strict";
class DocArchiver {}

// SyntaxError: class is a reserved identifier
// (throws in older browsers only, e.g. Firefox 44 and older)
```




 
See also 
--------

 
-   [Lexical grammar](../lexical_grammar)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Reserved_identifier>

