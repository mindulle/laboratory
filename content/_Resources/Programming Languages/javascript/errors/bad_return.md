SyntaxError: return not in function
===================================

 
The JavaScript exception \"return not in function\" occurs when a
[`return`](../statements/return) statement is called outside of a
[function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions).


 
Message
-------

 
```text
SyntaxError: Illegal return statement (V8-based)
SyntaxError: return not in function (Firefox)
SyntaxError: Return statements are only valid inside functions. (Safari)
```



 
Error type 
----------

 
[`SyntaxError`](../global_objects/syntaxerror).



 
What went wrong? 
----------------

 
A [`return`](../statements/return) statement is called outside of a
[function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions).
Maybe there are missing curly braces somewhere? The `return` statement
must be in a function, because it ends function execution and specifies
a value to be returned to the function caller.



 
Examples
--------


 
### Missing curly braces 

 
 
 
[js]


```js
function cheer(score) {
  if (score === 147)
    return "Maximum!";
  }
  if (score > 100) {
    return "Century!";
  }
}

// SyntaxError: return not in function
```


The curly braces look correct at a first glance, but this code snippet
is missing a `{` after the first `if` statement. Correct would be:

 
 
[js]


```js
function cheer(score) {
  if (score === 147) {
    return "Maximum!";
  }
  if (score > 100) {
    return "Century!";
  }
}
```




 
See also 
--------

 
-   [`return`](../statements/return)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Bad_return>

