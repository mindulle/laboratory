RegExp.prototype.sticky
=======================

 
The `sticky` accessor property of [`RegExp`](../regexp) instances
returns whether or not the `y` flag is used with this regular
expression.


 
Try it 
------

 



 
Description
-----------

 
`RegExp.prototype.sticky` has the value `true` if the `y` flag was used;
otherwise, `false`. The `y` flag indicates that the regex attempts to
match the target string only from the index indicated by the
[`lastIndex`](lastindex) property (and unlike a global regex, does not
attempt to match from any later indexes).

The set accessor of `sticky` is `undefined`. You cannot change this
property directly.

For both sticky regexes and [global](global) regexes:

-   They start matching at `lastIndex`.
-   When the match succeeds, `lastIndex` is advanced to the end of the
    match.
-   When `lastIndex` is out of bounds of the currently matched string,
    `lastIndex` is reset to 0.

However, for the [`exec()`](exec) method, the behavior when matching
fails is different:

-   When the [`exec()`](exec) method is called on a sticky regex, if the
    regex fails to match at `lastIndex`, the regex immediately returns
    `null` and resets `lastIndex` to 0.
-   When the [`exec()`](exec) method is called on a global regex, if the
    regex fails to match at `lastIndex`, it tries to match from the next
    character, and so on until a match is found or the end of the string
    is reached.

For the [`exec()`](exec) method, a regex that\'s both sticky and global
behaves the same as a sticky and non-global regex. Because
[`test()`](test) is a simple wrapper around `exec()`, `test()` would
ignore the global flag and perform sticky matches as well. However, due
to many other methods special-casing the behavior of global regexes, the
global flag is, in general, orthogonal to the sticky flag.

-   [`String.prototype.matchAll()`](../string/matchall) (which calls
    [`RegExp.prototype[@@matchAll]()`](@@matchall)): `y`, `g` and `gy`
    are all different.
    -   For `y` regexes: `matchAll()` throws; `[@@matchAll]()` yields
        the `exec()` result exactly once, without updating the regex\'s
        `lastIndex`.
    -   For `g` or `gy` regexes: returns an iterator that yields a
        sequence of `exec()` results.
-   [`String.prototype.match()`](../string/match) (which calls
    [`RegExp.prototype[@@match]()`](@@match)): `y`, `g` and `gy` are all
    different.
    -   For `y` regexes: returns the `exec()` result and updates the
        regex\'s `lastIndex`.
    -   For `g` or `gy` regexes: returns an array of all `exec()`
        results.
-   [`String.prototype.search()`](../string/search) (which calls
    [`RegExp.prototype[@@search]()`](@@search)): the `g` flag is always
    irrelevant.
    -   For `y` or `gy` regexes: always returns `0` (if the very
        beginning of the string matches) or `-1` (if the beginning
        doesn\'t match), without updating the regex\'s `lastIndex` when
        it exits.
    -   For `g` regexes: returns the index of the first match in the
        string, or `-1` if no match is found.
-   [`String.prototype.split()`](../string/split) (which calls
    [`RegExp.prototype[@@split]()`](@@split)): `y`, `g`, and `gy` all
    have the same behavior.
-   [`String.prototype.replace()`](../string/replace) (which calls
    [`RegExp.prototype[@@replace]()`](@@replace)): `y`, `g` and `gy` are
    all different.
    -   For `y` regexes: replaces once at the current `lastIndex` and
        updates `lastIndex`.
    -   For `g` and `gy` regexes: replaces all occurrences matched by
        `exec()`.
-   [`String.prototype.replaceAll()`](../string/replaceall) (which calls
    [`RegExp.prototype[@@replace]()`](@@replace)): `y`, `g` and `gy` are
    all different.
    -   For `y` regexes: `replaceAll()` throws.
    -   For `g` and `gy` regexes: replaces all occurrences matched by
        `exec()`.



 
Examples
--------


 
### Using a regular expression with the sticky flag 

 
 
 
[js]


```js
const str = "#foo#";
const regex = /foo/y;

regex.lastIndex = 1;
regex.test(str); // true
regex.lastIndex = 5;
regex.test(str); // false (lastIndex is taken into account with sticky flag)
regex.lastIndex; // 0 (reset after match failure)
```




 
### Anchored sticky flag 

 
For several versions, Firefox\'s SpiderMonkey engine had [a
bug](https://bugzil.la/773687) with regard to the `^` assertion and the
sticky flag which allowed expressions starting with the `^` assertion
and using the sticky flag to match when they shouldn\'t. The bug was
introduced some time after Firefox 3.6 (which had the sticky flag but
not the bug) and fixed in 2015. Perhaps because of the bug, the
specification [specifically calls
out](https://tc39.es/ecma262/multipage/text-processing.html#sec-compileassertion)
the fact that:

> Even when the `y` flag is used with a pattern, `^` always matches only
> at the beginning of *Input*, or (if *rer*.\[\[Multiline\]\] is `true`)
> at the beginning of a line.

Examples of correct behavior:

 
 
[js]


```js
const regex = /^foo/y;
regex.lastIndex = 2;
regex.test("..foo"); // false - index 2 is not the beginning of the string

const regex2 = /^foo/my;
regex2.lastIndex = 2;
regex2.test("..foo"); // false - index 2 is not the beginning of the string or line
regex2.lastIndex = 2;
regex2.test(".\nfoo"); // true - index 2 is the beginning of a line
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-regexp.prototype.sticky]](https://tc39.es/ecma262/multipage/text-processing.html#sec-get-regexp.prototype.sticky)

  -----------------------------------------------------------------------------------------------------------------------------------


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

`sticky`

49

13

3

36

10

49

4

36

10

5.0

49

1.0

6.0.0

`anchored_sticky_flag`

49

13

44

36

10

49

44

36

10

5.0

49

1.0

6.0.0

`prototype_accessor`

49

13

38

36

10

49

38

36

10

5.0

49

1.0

6.0.0

 
See also 
--------

 
-   [Polyfill of the `sticky` flag in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`RegExp.prototype.lastIndex`](lastindex)
-   [`RegExp.prototype.dotAll`](dotall)
-   [`RegExp.prototype.global`](global)
-   [`RegExp.prototype.hasIndices`](hasindices)
-   [`RegExp.prototype.ignoreCase`](ignorecase)
-   [`RegExp.prototype.multiline`](multiline)
-   [`RegExp.prototype.source`](source)
-   [`RegExp.prototype.unicode`](unicode)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/sticky>

