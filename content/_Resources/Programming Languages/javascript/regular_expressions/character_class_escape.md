Character class escape: \\d, \\D, \\w, \\W, \\s, \\S
====================================================

 
A **character class escape** is an escape sequence that represents a set
of characters.


 
Syntax
------

 
 
 
[regex]


```regex
\d, \D
\s, \S
\w, \W
```


 
**Note:** `,` is not part of the syntax.




 
Description
-----------

 
Unlike [character escapes](character_escape), character class escapes
represent a predefined *set* of characters, much like a [character
class](character_class). The following character classes are supported:

[`\d`](#d)

:   Matches any digit character. Equivalent to `[0-9]`.

[`\w`](#w)

:   Matches any word character, where a word character includes letters
    (A--Z, a--z), numbers (0--9), and underscore (\_). If the regex is
    [Unicode-aware](../global_objects/regexp/unicode#unicode-aware_mode)
    and the [`i`](../global_objects/regexp/ignorecase) flag is set, it
    also matches other Unicode characters that get canonicalized to one
    of the characters above through [case
    folding](https://unicode.org/Public/UCD/latest/ucd/CaseFolding.txt).

[`\s`](#s)

:   Matches any [whitespace](../lexical_grammar#white_space) or [line
    terminator](../lexical_grammar#line_terminators) character.

The uppercase forms `\D`, `\W`, and `\S` create complement character
classes for `\d`, `\w`, and `\s`, respectively. They match any character
that is not in the set of characters matched by the lowercase form.

[Unicode character class escapes](unicode_character_class_escape) start
with `\p` and `\P`, but they are only supported in [Unicode-aware
mode](../global_objects/regexp/unicode#unicode-aware_mode). In
Unicode-unaware mode, they are [identity escapes](character_escape) for
the `p` or `P` character.

Character class escapes can be used in [character
classes](character_class). However, they cannot be used as boundaries of
character ranges, which is only allowed as a [deprecated syntax for web
compatibility](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features#regexp),
and you should not rely on it.



 
Examples
--------


 
### Splitting by whitespace 

 
The following example splits a string into an array of words, supporting
all kinds of whitespace separators:

 
 
[js]


```js
function splitWords(str) {
  return str.split(/\s+/);
}

splitWords(`Look at the stars
Look  how they\tshine for you`);
// ['Look', 'at', 'the', 'stars', 'Look', 'how', 'they', 'shine', 'for', 'you']
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  prod-CharacterClassEscape]](https://tc39.es/ecma262/multipage/text-processing.html#prod-CharacterClassEscape)

  -----------------------------------------------------------------------------------------------------------------------


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

`Character_class_escape`

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

 
-   [Character
    classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions/Character_classes)
    guide
-   [Regular expressions](../regular_expressions)
-   [Character class: `[...]`, `[^...]`](character_class)
-   [Unicode character class escape: `\p`,
    `\P`](unicode_character_class_escape)
-   [Character escape: `\n`, `\u`](character_escape)
-   [Disjunction: `|`](disjunction)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Character_class_escape>

