RegExp.prototype.unicode
========================

 
The `unicode` accessor property of [`RegExp`](../regexp) instances
returns whether or not the `u` flag is used with this regular
expression.


 
Try it 
------

 



 
Description
-----------

 
`RegExp.prototype.unicode` has the value `true` if the `u` flag was
used; otherwise, `false`. The `u` flag enables various Unicode-related
features. With the \"u\" flag:

-   Any [Unicode code point
    escapes](../../regular_expressions/unicode_character_class_escape)
    (`\u{xxxx}`, `\p{UnicodePropertyValue}`) will be interpreted as such
    instead of identity escapes. For example `/\u{61}/u` matches `"a"`,
    but `/\u{61}/` (without `u` flag) matches `"u".repeat(61)`, where
    the `\u` is equivalent to a single `u`.
-   Surrogate pairs will be interpreted as whole characters instead of
    two separate characters. For example, `/[😄]/u` would only match
    `"😄"` but not `"\ud83d"`.
-   When [`lastIndex`](lastindex) is automatically advanced (such as
    when calling [`exec()`](exec)), unicode regexes advance by Unicode
    code points instead of UTF-16 code units.

There are other changes to the parsing behavior that prevent possible
syntax mistakes (which are analogous to [strict mode](../../strict_mode)
for regex syntax). These syntaxes are all [deprecated and only kept for
web
compatibility](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features#regexp),
and you should not rely on them.

The set accessor of `unicode` is `undefined`. You cannot change this
property directly.



 
### Unicode-aware mode 

 
When we refer to *Unicode-aware mode*, we mean the regex has either the
`u` or the [`v`](unicodesets) flag, in which case the regex enables
Unicode-related features (such as [Unicode character class
escape](../../regular_expressions/unicode_character_class_escape)) and
has much stricter syntax rules. Because `u` and `v` interpret the same
regex in incompatible ways, using both flags results in a
[`SyntaxError`](../syntaxerror).

Similarly, a regex is *Unicode-unaware* if it has neither the `u` nor
the `v` flag. In this case, the regex is interpreted as a sequence of
UTF-16 code units, and there are many legacy syntaxes that do not become
syntax errors.



 
Examples
--------


 
### Using the unicode property 

 
 
 
[js]


```js
const regex = /\u{61}/u;

console.log(regex.unicode); // true
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-regexp.prototype.unicode]](https://tc39.es/ecma262/multipage/text-processing.html#sec-get-regexp.prototype.unicode)

  -------------------------------------------------------------------------------------------------------------------------------------


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

`unicode`

50

12Case folding is implemented in version 13

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

6.0.0Case folding is implemented in version 8.6.0

 
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



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/unicode>

