SyntaxError: \"0\"-prefixed octal literals and octal escape seq. are deprecated
===============================================================================


The JavaScript [strict mode](../strict_mode)-only exception \"0-prefixed
octal literals and octal escape sequences are deprecated; for octal
literals use the \"0o\" prefix instead\" occurs when deprecated octal
literals and octal escape sequences are used.



Message
-------


```text
SyntaxError: Octal literals are not allowed in strict mode. (V8-based)
SyntaxError: "0"-prefixed octal literals are deprecated; use the "0o" prefix instead (Firefox)
SyntaxError: Decimal integer literals with a leading zero are forbidden in strict mode (Safari)

SyntaxError: Octal escape sequences are not allowed in strict mode. (V8-based)
SyntaxError: octal escape sequences can't be used in untagged template literals or in strict mode code (Firefox)
SyntaxError: The only valid numeric escape in strict mode is '\0' (Safari)
```




Error type 
----------


[`SyntaxError`](../global_objects/syntaxerror) in [strict
mode](../strict_mode) only.




What went wrong? 
----------------


Octal literals and octal escape sequences are deprecated and will throw
a [`SyntaxError`](../global_objects/syntaxerror) in strict mode. The
standardized syntax uses a leading zero followed by a lowercase or
uppercase Latin letter \"O\" (`0o` or `0O`).




Examples
--------



### \"0\"-prefixed octal literals 




[js]


```js
"use strict";

03;

// SyntaxError: "0"-prefixed octal literals are deprecated; use the "0o" prefix instead
```





### Octal escape sequences 




[js]


```js
"use strict";

"\251";

// SyntaxError: octal escape sequences can't be used in untagged template literals or in strict mode code
```





### Valid octal numbers 


Use a leading zero followed by the letter \"o\" or \"O\":



[js]


```js
0o3;
```


For octal escape sequences, you can use hexadecimal escape sequences
instead:



[js]


```js
"\xA9";
```





See also 
--------


-   [Lexical grammar](../lexical_grammar#octal)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Deprecated_octal>

