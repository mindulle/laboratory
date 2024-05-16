RegExp() constructor
====================

 
The `RegExp()` constructor creates [`RegExp`](../regexp) objects.

For an introduction to regular expressions, read the [Regular
Expressions
chapter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions)
in the [JavaScript
Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new RegExp(pattern)
new RegExp(pattern, flags)
RegExp(pattern)
RegExp(pattern, flags)
```


 
**Note:** `RegExp()` can be called with or without
[`new`](../../operators/new), but sometimes with different effects. See
[Return value](#return_value).




 
### Parameters

 

[`pattern`](#pattern)

:   The text of the regular expression. This can also be another
    `RegExp` object.

[`flags`](#flags) [Optional]

:   If specified, `flags` is a string that contains the flags to add.
    Alternatively, if a `RegExp` object is supplied for the `pattern`,
    the `flags` string will replace any of that object\'s flags (and
    `lastIndex` will be reset to `0`).

    `flags` may contain any combination of the following characters:

    [`d` (indices)](hasindices)

    :   Generate indices for substring matches.

    [`g` (global)](global)

    :   Find all matches rather than stopping after the first match.

    [`i` (ignore case)](ignorecase)

    :   When matching, casing differences are ignored.

    [`m` (multiline)](multiline)

    :   Treat beginning and end assertions (`^` and `$`) as working over
        multiple lines. In other words, match the beginning or end of
        *each* line (delimited by `\n` or `\r`), not only the very
        beginning or end of the whole input string.

    [`s` (dotAll)](dotall)

    :   Allows `.` to match newlines.

    [`u` (unicode)](unicode)

    :   Treat `pattern` as a sequence of Unicode code points.

    [`v` (unicodeSets)](unicodesets)

    :   An upgrade to the `u` flag that enables set notation in
        character classes as well as properties of strings.

    [`y` (sticky)](sticky)

    :   Matches only from the index indicated by the `lastIndex`
        property of this regular expression in the target string. Does
        not attempt to match from any later indexes.



 
### Return value 

 
`RegExp(pattern)` returns `pattern` directly if all of the following are
true:

-   `RegExp()` is called without [`new`](../../operators/new);
-   [`pattern` is a regex](../regexp#special_handling_for_regexes);
-   `pattern.constructor === RegExp` (usually meaning it\'s not a
    subclass);
-   `flags` is `undefined`.

In all other cases, calling `RegExp()` with or without `new` both create
a new `RegExp` object. If `pattern` is a regex, the new object\'s
[source](source) is `pattern.source`; otherwise, its source is `pattern`
[coerced to a string](../string#string_coercion). If the `flags`
parameter is not `undefined`, the new object\'s [`flags`](flags) is the
parameter\'s value; otherwise, its `flags` is `pattern.flags` (if
`pattern` is a regex).



 
### Exceptions

 

[`SyntaxError`](../syntaxerror)

:   Thrown in one of the following cases:

    -   `pattern` cannot be parsed as a valid regular expression.
    -   `flags` contains repeated characters or any character outside of
        those allowed.



 
Examples
--------


 
### Literal notation and constructor 

 
There are two ways to create a `RegExp` object: a *literal notation* and
a *constructor*.

-   The *literal notation* takes a pattern between two slashes, followed
    by optional flags, after the second slash.
-   The *constructor function* takes either a string or a `RegExp`
    object as its first parameter and a string of optional flags as its
    second parameter.

The following three expressions create the same regular expression:

 
 
[js]


```js
/ab+c/i;
new RegExp(/ab+c/, "i"); // literal notation
new RegExp("ab+c", "i"); // constructor
```


Before regular expressions can be used, they have to be compiled. This
process allows them to perform matches more efficiently. There are two
ways to compile and get a `RegExp` object.

The literal notation results in compilation of the regular expression
when the expression is evaluated. On the other hand, the constructor of
the `RegExp` object, `new RegExp('ab+c')`, results in runtime
compilation of the regular expression.

Use a string as the first argument to the `RegExp()` constructor when
you want to [build the regular expression from dynamic
input](#building_a_regular_expression_from_dynamic_inputs).



 
### Building a regular expression from dynamic inputs 

 
 
 
[js]


```js
const breakfasts = ["bacon", "eggs", "oatmeal", "toast", "cereal"];
const order = "Let me get some bacon and eggs, please";

order.match(new RegExp(`\\b(${breakfasts.join("|")})\\b`, "g"));
// Returns ['bacon', 'eggs']
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-regexp-constructor]](https://tc39.es/ecma262/multipage/text-processing.html#sec-regexp-constructor)

  -----------------------------------------------------------------------------------------------------------------


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

`RegExp`

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

 
-   [Polyfill of many modern `RegExp` features (`dotAll`, `sticky`
    flags, named capture groups, etc.) in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [Regular
    expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions)
    guide
-   [`String.prototype.match()`](../string/match)
-   [`String.prototype.replace()`](../string/replace)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/RegExp>

