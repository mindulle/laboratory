RegExp.prototype.ignoreCase
===========================

 
The `ignoreCase` accessor property of [`RegExp`](../regexp) instances
returns whether or not the `i` flag is used with this regular
expression.


 
Try it 
------

 



 
Description
-----------

 
`RegExp.prototype.ignoreCase` has the value `true` if the `i` flag was
used; otherwise, `false`. The `i` flag indicates that case should be
ignored while attempting a match in a string. Case-insensitive matching
is done by mapping both the expected character set and the matched
string to the same casing.

If the regex is [Unicode-aware](unicode#unicode-aware_mode), the case
mapping happens through *simple case folding* specified in
[`CaseFolding.txt`](https://unicode.org/Public/UCD/latest/ucd/CaseFolding.txt).
The mapping always maps to a single code point, so it does not map, for
example, `ß` (U+00DF LATIN SMALL LETTER SHARP S) to `ss` (which is *full
case folding*, not *simple case folding*). It may however map code
points outside the Basic Latin block to code points within it --- for
example, `ſ` (U+017F LATIN SMALL LETTER LONG S) case-folds to `s`
(U+0073 LATIN SMALL LETTER S) and `K` (U+212A KELVIN SIGN) case-folds to
`k` (U+006B LATIN SMALL LETTER K). Therefore, `ſ` and `K` can be matched
by `/[a-z]/ui`.

If the regex is Unicode-unaware, case mapping uses the [Unicode Default
Case
Conversion](https://unicode-org.github.io/icu/userguide/transforms/casemappings.html)
--- the same algorithm used in
[`String.prototype.toUpperCase()`](../string/touppercase). For example,
`Ω` (U+2126 OHM SIGN) and `Ω` (U+03A9 GREEK CAPITAL LETTER OMEGA) are
both mapped by Default Case Conversion to themselves but by simple case
folding to `ω` (U+03C9 GREEK SMALL LETTER OMEGA), so `"ω"` is matched by
`/[\u2126]/ui` and `/[\u03a9]/ui` but not by `/[\u2126]/i` or
`/[\u03a9]/i`. This algorithm prevents code points outside the Basic
Latin block to be mapped to code points within it, so `ſ` and `K`
mentioned previously are not matched by `/[a-z]/i`.

The set accessor of `ignoreCase` is `undefined`. You cannot change this
property directly.



 
Examples
--------


 
### Using ignoreCase 

 
 
 
[js]


```js
const regex = /foo/i;

console.log(regex.ignoreCase); // true
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-regexp.prototype.ignorecase]](https://tc39.es/ecma262/multipage/text-processing.html#sec-get-regexp.prototype.ignorecase)

  -------------------------------------------------------------------------------------------------------------------------------------------


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

`ignoreCase`

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

`prototype_accessor`

48

12

38

35

1.3

48

38

35

1

5.0

48

1.0

6.0.0

 
See also 
--------

 
-   [`RegExp.prototype.lastIndex`](lastindex)
-   [`RegExp.prototype.dotAll`](dotall)
-   [`RegExp.prototype.global`](global)
-   [`RegExp.prototype.hasIndices`](hasindices)
-   [`RegExp.prototype.multiline`](multiline)
-   [`RegExp.prototype.source`](source)
-   [`RegExp.prototype.sticky`](sticky)
-   [`RegExp.prototype.unicode`](unicode)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/ignoreCase>

