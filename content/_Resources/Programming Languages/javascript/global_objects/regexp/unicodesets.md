RegExp.prototype.unicodeSets
============================

 
The `unicodeSets` accessor property of [`RegExp`](../regexp) instances
returns whether or not the `v` flag is used with this regular
expression.


 
Description
-----------

 
`RegExp.prototype.unicodeSets` has the value `true` if the `v` flag was
used; otherwise, `false`. The `v` flag is an \"upgrade\" to the
[`u`](unicode) flag that enables more Unicode-related features. (\"v\"
is the next letter after \"u\" in the alphabet.) Because `u` and `v`
interpret the same regex in incompatible ways, using both flags results
in a [`SyntaxError`](../syntaxerror). With the `v` flag, you get all
features mentioned in the `u` flag description, plus:

-   The [`\p`](../../regular_expressions/unicode_character_class_escape)
    escape sequence can be additionally used to match properties of
    strings, instead of just characters.
-   The [character class](../../regular_expressions/character_class)
    syntax is upgraded to allow intersection, union, and subtraction
    syntaxes, as well as matching multiple Unicode characters.
-   The character class complement syntax `[^...]` constructs a
    complement class instead of negating the match result, avoiding some
    confusing behaviors with case-insensitive matching. For more
    information, see [Complement classes and case-insensitive
    matching](../../regular_expressions/character_class#complement_classes_and_case-insensitive_matching).

Some valid `u`-mode regexes become invalid in `v`-mode. Specifically,
the character class syntax is different and some characters can no
longer appear literally. For more information, see [`v`-mode character
class](../../regular_expressions/character_class#v-mode_character_class).

 
**Note:** The `v` mode does not interpret grapheme clusters as single
characters; they are still multiple code points. For example, `/[🇺🇳]/v`
is still able to match `"🇺"`.


The set accessor of `unicodeSets` is `undefined`. You cannot change this
property directly.



 
Examples
--------


 
### Using the unicodeSets property 

 
 
 
[js]


```js
const regex = /[\p{Script_Extensions=Greek}&&\p{Letter}]/v;

console.log(regex.unicodeSets); // true
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-regexp.prototype.unicodesets]](https://tc39.es/ecma262/multipage/text-processing.html#sec-get-regexp.prototype.unicodesets)

  ---------------------------------------------------------------------------------------------------------------------------------------------


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

`unicodeSets`

112

112

116

98

17

112

116

75

17

23.0

112

1.32

20.0.0

 
See also 
--------

 
-   [`RegExp.prototype.lastIndex`](lastindex)
-   [`RegExp.prototype.dotAll`](dotall)
-   [`RegExp.prototype.global`](global)
-   [`RegExp.prototype.hasIndices`](hasindices)
-   [`RegExp.prototype.ignoreCase`](ignorecase)
-   [`RegExp.prototype.multiline`](multiline)
-   [`RegExp.prototype.source`](source)
-   [`RegExp.prototype.sticky`](sticky)
-   [`RegExp.prototype.unicode`](unicode)
-   [RegExp v flag with set notation and properties of
    strings](https://v8.dev/features/regexp-v-flag) on v8.dev (2022)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/unicodeSets>

