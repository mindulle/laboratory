Literal character: a, b
=======================

 
A **literal character** specifies exactly itself to be matched in the
input text.


 
Syntax
------

 
 
 
[regex]


```regex
c
```




 
### Parameters

 

[`c`](#c)

:   A single character that is not one of the syntax characters
    described below.



 
Description
-----------

 
In regular expressions, most characters can appear literally. They are
usually the most basic building blocks of patterns. For example, here is
a pattern from the [Removing HTML tags](quantifier#removing_html_tags)
example:

 
 
[js]


```js
const pattern = /<.+?>/g;
```


In this example, `.`, `+`, and `?` are called *syntax characters*. They
have special meanings in regular expressions. The rest of the characters
in the pattern (`<` and `>`) are literal characters. They match
themselves in the input text: the left and right angle brackets.

The following characters are syntax characters in regular expressions,
and they cannot appear as literal characters:

-   [`^`, `$`](input_boundary_assertion)
-   [`\`](character_escape)
-   [`*`, `+`, `?`, `{`, `}`](quantifier)
-   [`(`, `)`](capturing_group)
-   [`[`, `]`](character_class)
-   [`|`](disjunction)

Within character classes, more characters can appear literally. For more
information, see the [Character class](character_class) page. For
example `\.` and `[.]` both match a literal `.`. In [`v`-mode character
classes](character_class#v-mode_character_class), however, there are a
different set of characters reserved as syntax characters. To be most
comprehensive, below is a table of ASCII characters and whether they may
appear escaped or unescaped in different contexts, where \"✅\" means the
character represents itself, \"❌\" means it throws a syntax error, and
\"⚠️\" means the character is valid but means something other than
itself.

 
Characters




Outside character classes in `u` or `v` mode

In `u`-mode character classes

In `v`-mode character classes

Unescaped

Escaped

Unescaped

Escaped

Unescaped

Escaped

`123456789 "'ACEFGHIJKLMNOPQRTUVXYZ_aceghijklmopquxyz`

✅

❌

✅

❌

✅

❌

`` !#%&,:;<=>@`~ ``

✅

❌

✅

❌

✅

✅

`]`

❌

✅

❌

✅

❌

✅

`()[{}`

❌

✅

✅

✅

❌

✅

`*+?`

❌

✅

✅

✅

✅

✅

`/`

✅

✅

✅

✅

❌

✅

`0DSWbdfnrstvw`

✅

⚠️

✅

⚠️

✅

⚠️

`B`

✅

⚠️

✅

❌

✅

❌

`$.`

⚠️

✅

✅

✅

✅

✅

`|`

⚠️

✅

✅

✅

❌

✅

`-`

✅

❌

✅⚠️

✅

❌⚠️

✅

`^`

⚠️

✅

✅⚠️

✅

✅⚠️

✅

`\`

❌⚠️

✅

❌⚠️

✅

❌⚠️

✅

 
**Note:** The characters that can both be escaped and unescaped in
`v`-mode character classes are exactly those forbidden as \"double
punctuators\". See [`v`-mode character
classes](character_class#v-mode_character_class) for more information.


Whenever you want to match a syntax character literally, you need to
[escape](character_escape) it with a backslash (`\`). For example, to
match a literal `*` in a pattern, you need to write `\*` in the pattern.
Using syntax characters as literal characters either leads to unexpected
results or causes syntax errors --- for example, `/*/` is not a valid
regular expression because the quantifier is not preceded by a pattern.
In [Unicode-unaware
mode](../global_objects/regexp/unicode#unicode-aware_mode), `]`, `{`,
and `}` may appear literally if it\'s not possible to parse them as the
end of a character class or quantifier delimiters. This is a [deprecated
syntax for web
compatibility](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features#regexp),
and you should not rely on it.

Regular expression literals cannot be specified with certain non-syntax
literal characters. `/` cannot appear as a literal character in a
regular expression literal, because `/` is used as the delimiter of the
literal itself. You need to escape it as `\/` if you want to match a
literal `/`. Line terminators cannot appear as literal characters in a
regular expression literal either, because a literal cannot span
multiple lines. You need to use a [character escape](character_escape)
like `\n` instead. There are no such restrictions when using the
[`RegExp()`](../global_objects/regexp/regexp) constructor, although
string literals have their own escaping rules (for example, `"\\"`
actually denotes a single backslash character, so `new RegExp("\\*")`
and `/\*/` are equivalent).

In [Unicode-unaware
mode](../global_objects/regexp/unicode#unicode-aware_mode), the pattern
is interpreted as a sequence of [UTF-16 code
units](../global_objects/string#utf-16_characters_unicode_code_points_and_grapheme_clusters).
This means surrogate pairs actually represent two literal characters.
This causes unexpected behaviors when paired with other features:

 
 
[js]


```js
/^[😄]$/.test("😄"); // false, because the pattern is interpreted as /^[\ud83d\udc04]$/
/^😄+$/.test("😄😄"); // false, because the pattern is interpreted as /^\ud83d\udc04+$/
```


In Unicode-aware mode, the pattern is interpreted as a sequence of
Unicode code points, and surrogate pairs do not get split. Therefore,
you should always prefer to use the `u` flag.

 
Examples
--------


 
### Using literal characters 

 
The following example is copied from [Character
escape](character_escape#using_character_escapes). The `a` and `b`
characters are literal characters in the pattern, and `\n` is an escaped
character because it cannot appear literally in a regular expression
literal.

 
 
[js]


```js
const pattern = /a\nb/;
const string = `a
b`;
console.log(pattern.test(string)); // true
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  prod-PatternCharacter]](https://tc39.es/ecma262/multipage/text-processing.html#prod-PatternCharacter)

  ---------------------------------------------------------------------------------------------------------------


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

`Literal_character`

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
-   [Character escape: `\n`, `\u`](character_escape)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Literal_character>

