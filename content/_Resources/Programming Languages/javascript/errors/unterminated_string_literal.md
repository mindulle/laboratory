SyntaxError: unterminated string literal
========================================

 
The JavaScript error \"unterminated string literal\" occurs when there
is an unterminated [string
literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#string_literals)
somewhere. String literals must be enclosed by single (`'`) or double
(`"`) quotes.


 
Message
-------

 
```text
SyntaxError: Unterminated string constant (Edge)
SyntaxError: unterminated string literal (Firefox)
```



 
Error type 
----------

 
[`SyntaxError`](../global_objects/syntaxerror)



 
What went wrong? 
----------------

 
There is an unterminated [string
literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#string_literals)
somewhere. String literals must be enclosed by single (`'`) or double
(`"`) quotes. JavaScript makes no distinction between single-quoted
strings and double-quoted strings. [Escape
sequences](../lexical_grammar#escape_sequences) work in strings created
with either single or double quotes. To fix this error, check if:

-   you have opening and closing quotes (single or double) for your
    string literal,
-   you have escaped your string literal correctly,
-   your string literal isn\'t split across multiple lines.



 
Examples
--------


 
### Multiple lines 

 
You can\'t split a string across multiple lines like this in JavaScript:

 
 
[js]


```js
const longString = "This is a very long string which needs
                    to wrap across multiple lines because
                    otherwise my code is unreadable.";
// SyntaxError: unterminated string literal
```


Instead, use the [+ operator](../operators/addition), a backslash, or
[template literals](../template_literals). The `+` operator variant
looks like this:

 
 
[js]


```js
const longString =
  "This is a very long string which needs " +
  "to wrap across multiple lines because " +
  "otherwise my code is unreadable.";
```


Or you can use the backslash character (\"\\\") at the end of each line
to indicate that the string will continue on the next line. Make sure
there is no space or any other character after the backslash (except for
a line break), or as an indent; otherwise it will not work. That form
looks like this:

 
 
[js]


```js
const longString =
  "This is a very long string which needs \
to wrap across multiple lines because \
otherwise my code is unreadable.";
```


Another possibility is to use [template literals](../template_literals).

 
 
[js]


```js
const longString = `This is a very long string which needs 
to wrap across multiple lines because 
otherwise my code is unreadable.`;
```




 
See also 
--------

 
-   [string
    literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#string_literals)
-   [Template literals](../template_literals)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Unterminated_string_literal>

