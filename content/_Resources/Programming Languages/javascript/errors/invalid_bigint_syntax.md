SyntaxError: invalid BigInt syntax
==================================

 
The JavaScript exception \"invalid BigInt syntax\" occurs when a string
value is being coerced to a [`BigInt`](../global_objects/bigint) but it
failed to be parsed as an integer.


 
Message
-------

 
```text
SyntaxError: Cannot convert x to a BigInt (V8-based)
SyntaxError: invalid BigInt syntax (Firefox)
SyntaxError: Failed to parse String to BigInt (Safari)
```



 
Error type 
----------

 
[`SyntaxError`](../global_objects/syntaxerror).



 
What went wrong? 
----------------

 
When using the [`BigInt()`](../global_objects/bigint/bigint) function to
convert a string to a BigInt, the string will be parsed in the same way
as source code, and the resulting value must be an integer value.



 
Examples
--------


 
### Invalid cases 

 
 
 
[js]


```js
const a = BigInt("1.5");
const b = BigInt("1n");
const c = BigInt.asIntN(4, "8n");
// SyntaxError: invalid BigInt syntax
```




 
### Valid cases 

 
 
 
[js]


```js
const a = BigInt("1");
const b = BigInt("  1   ");
const c = BigInt.asIntN(4, "8");
```




 
See also 
--------

 
-   [`BigInt`](../global_objects/bigint)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_BigInt_syntax>

