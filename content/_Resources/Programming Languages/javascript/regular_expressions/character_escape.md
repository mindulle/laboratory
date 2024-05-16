Character escape: \\n, \\u\{\...\}
================================

 
A **character escape** represents a character that may not be able to be
conveniently represented in its literal form.


 
Syntax
------

 
 
 
[regex]


```regex
\f, \n, \r, \t, \v
\cA, \cB, …, \cz
\0
\^, \$, \\, \., \*, \+, \?, \(, \), \[, \], {, }, \|, \/

\xHH
\uHHHH
\u{HHH}
```


 
**Note:** `,` is not part of the syntax.




 
### Parameters

 

[`HHH`](#hhh)

:   A hexadecimal number representing the Unicode code point of the
    character. The `\xHH` form must have two hexadecimal digits; the
    `\uHHHH` form must have four; the `\u{HHH}` form may have 1 to 6
    hexadecimal digits.



 
Description
-----------

 
The following character escapes are recognized in regular expressions:

[`\f`](#f), `\n`, `\r`, `\t`, `\v`

:   Same as those in [string
    literals](../lexical_grammar#escape_sequences), except `\b`, which
    represents a [word boundary](word_boundary_assertion) in regexes
    unless in a [character class](character_class).

[`\c`](#c) followed by a letter from `A` to `Z` or `a` to `z`

:   Represents the control character with value equal to the letter\'s
    character value modulo 32. For example, `\cJ` represents line break
    (`\n`), because the code point of `J` is 74, and 74 modulo 32 is 10,
    which is the code point of line break. Because an uppercase letter
    and its lowercase form differ by 32, `\cJ` and `\cj` are equivalent.
    You can represent control characters from 1 to 26 in this form.

[`\0`](#0)

:   Represents the U+0000 NUL character. Cannot be followed by a digit
    (which makes it a [legacy octal
    escape](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features#escape_sequences)
    sequence).

[`\^`](#sect2), `\$`, `\\`, `\.` `\*`, `\+`, `\?`, `\(`, `\)`, `\[`, `\]`, `{`, `}`, `\|`, `\/`

:   Represents the character itself. For example, `\\` represents a
    backslash, and `\(` represents a left parenthesis. These are [syntax
    characters](literal_character) in regexes (`/` is the delimiter of a
    regex literal), so they require escaping unless in a [character
    class](character_class).

[`\xHH`](#xhh)

:   Represents the character with the given hexadecimal Unicode code
    point. The hexadecimal number must be exactly two digits long.

[`\uHHHH`](#uhhhh)

:   Represents the character with the given hexadecimal Unicode code
    point. The hexadecimal number must be exactly four digits long. Two
    such escape sequences can be used to represent a surrogate pair in
    [Unicode-aware
    mode](../global_objects/regexp/unicode#unicode-aware_mode). (In
    Unicode-unaware mode, they are always two separate characters.)

[`\u{HHH}`](#uhhh)

:   ([Unicode-aware
    mode](../global_objects/regexp/unicode#unicode-aware_mode) only)
    Represents the character with the given hexadecimal Unicode code
    point. The hexadecimal number can be from 1 to 6 digits long.

In [Unicode-unaware
mode](../global_objects/regexp/unicode#unicode-aware_mode), escape
sequences that are not one of the above become *identity escapes*: they
represent the character that follows the backslash. For example, `\a`
represents the character `a`. This behavior limits the ability to
introduce new escape sequences without causing backward compatibility
issues, and is therefore forbidden in Unicode-aware mode.

In Unicode-unaware mode, `]`, `{`, and `}` may appear
[literally](literal_character) if it\'s not possible to parse them as
the end of a character class or quantifier delimiters. This is a
[deprecated syntax for web
compatibility](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features#regexp),
and you should not rely on it.

In Unicode-unaware mode, escape sequences within [character
classes](character_class) of the form `\cX` where `X` is a number or `_`
are decoded in the same way as those with
[ASCII](https://developer.mozilla.org/en-US/docs/Glossary/ASCII)
letters: `\c0` is the same as `\cP` when taken modulo 32. In addition,
if the form `\cX` is encountered anywhere where `X` is not one of the
recognized characters, then the backslash is treated as a literal
character. These syntaxes are also deprecated.

 
 
[js]


```js
/[\c0]/.test("\x10"); // true
/[\c_]/.test("\x1f"); // true
/[\c*]/.test("\\"); // true
/\c/.test("\\c"); // true
/\c0/.test("\\c0"); // true (the \c0 syntax is only supported in character classes)
```




 
Examples
--------


 
### Using character escapes 

 
Character escapes are useful when you want to match a character that is
not easily represented in its literal form. For example, you cannot use
a line break literally in a regex literal, so you must use a character
escape:

 
 
[js]


```js
const pattern = /a\nb/;
const string = `a
b`;
console.log(pattern.test(string)); // true
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  prod-CharacterEscape]](https://tc39.es/ecma262/multipage/text-processing.html#prod-CharacterEscape)

  -------------------------------------------------------------------------------------------------------------


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

`Character_escape`

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

`unicode`

50

12

46

37

10

50

46

37

10

5.0

50

1.0

6.0.0

 
See also 
--------

 
-   [Character
    classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions/Character_classes)
    guide
-   [Regular expressions](../regular_expressions)
-   [Character class: `[...]`, `[^...]`](character_class)
-   [Character class escape: `\d`, `\D`, `\w`, `\W`, `\s`,
    `\S`](character_class_escape)
-   [Literal character: `a`, `b`](literal_character)
-   [Unicode character class escape: `\p`,
    `\P`](unicode_character_class_escape)
-   [Backreference: `\1`, `\2`](backreference)
-   [Named backreference: `\k<name>`](named_backreference)
-   [Word boundary assertion: `\b`, `\B`](word_boundary_assertion)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Character_escape>

