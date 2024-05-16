Word boundary assertion: \\b, \\B
=================================

 
A **word boundary assertion** checks if the current position in the
string is a word boundary. A word boundary is where the next character
is a word character and the previous character is not a word character,
or vice versa.


 
Syntax
------

 
 
 
[regex]


```regex
\b
\B
```




 
Description
-----------

 
`\b` asserts that the current position in the string is a word boundary.
`\B` negates the assertion: it asserts that the current position is not
a word boundary. Both are *assertions*, so unlike other [character
escapes](character_escape) or [character class
escapes](character_class_escape), `\b` and `\B` don\'t consume any
characters.

A word character includes the following:

-   Letters (A--Z, a--z), numbers (0--9), and underscore (\_).
-   If the regex is
    [Unicode-aware](../global_objects/regexp/unicode#unicode-aware_mode)
    and the [`i`](../global_objects/regexp/ignorecase) flag is set,
    other Unicode characters that get canonicalized to one of the
    characters above through [case
    folding](https://unicode.org/Public/UCD/latest/ucd/CaseFolding.txt).

Word characters are also matched by the `\w` [character class
escape](character_class_escape).

Out-of-bounds input positions are considered non-word characters. For
example, the following are successful matches:

 
 
[js]


```js
/\ba/.exec("abc");
/c\b/.exec("abc");

/\B /.exec(" abc");
/ \B/.exec("abc ");
```




 
Examples
--------


 
### Detecting words 

 
The following example detects if a string contains the word \"thanks\"
or \"thank you\":

 
 
[js]


```js
function hasThanks(str) {
  return /\b(thanks|thank you)\b/i.test(str);
}

hasThanks("Thanks! You helped me a lot."); // true
hasThanks("Just want to say thank you for all your work."); // true
hasThanks("Thanksgiving is around the corner."); // false
```


 
**Warning:** Not all languages have clearly defined word boundaries. If
you are working with languages like Chinese or Thai, where there are no
whitespace separators, use a more advanced library like
[`Intl.Segmenter`](../global_objects/intl/segmenter) to search for words
instead.




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  prod-Assertion]](https://tc39.es/ecma262/multipage/text-processing.html#prod-Assertion)

  -------------------------------------------------------------------------------------------------


Browser compatibility 
---------------------

 


Desktop

Mobile

Server

Chrome

Edge

Firefox

Opera

Safari

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

WebView Android

Deno

Node.js

`Word_boundary_assertion`

1

12

1

5

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [Assertions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions/Assertions)
    guide
-   [Regular expressions](../regular_expressions)
-   [Input boundary assertion: `^`, `$`](input_boundary_assertion)
-   [Lookahead assertion: `(?=...)`, `(?!...)`](lookahead_assertion)
-   [Lookbehind assertion: `(?<=...)`, `(?<!...)`](lookbehind_assertion)
-   [Character escape: `\n`, `\u`](character_escape)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Word_boundary_assertion>

