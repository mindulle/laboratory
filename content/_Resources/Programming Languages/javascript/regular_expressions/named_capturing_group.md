Named capturing group: (?\<name\>\...)
======================================

 
A **named capturing group** is a particular kind of [capturing
group](capturing_group) that allows to give a name to the group. The
group\'s matching result can later be identified by this name instead of
by its index in the pattern.


 
Syntax
------

 
 
 
[regex]


```regex
(?<name>pattern)
```




 
### Parameters

 

[`pattern`](#pattern)

:   A pattern consisting of anything you may use in a regex literal,
    including a [disjunction](disjunction).

[`name`](#name)

:   The name of the group. Must be a valid
    [identifier](../lexical_grammar#identifiers).



 
Description
-----------

 
Named capturing groups can be used just like capturing groups --- they
also have their match index in the result array, and they can be
referenced through `\1`, `\2`, etc. The only difference is that they can
be *additionally* referenced by their name. The information of the
capturing group\'s match can be accessed through:

-   The `groups` property of the return value of
    [`RegExp.prototype.exec()`](../global_objects/regexp/exec),
    [`String.prototype.match()`](../global_objects/string/match), and
    [`String.prototype.matchAll()`](../global_objects/string/matchall)
-   The `groups` parameter of the
    [`String.prototype.replace()`](../global_objects/string/replace) and
    [`String.prototype.replaceAll()`](../global_objects/string/replaceall)
    methods\' `replacement` callback function
-   [Named backreferences](named_backreference) within the same pattern

All names must be unique within the same pattern. Multiple named
capturing groups with the same name result in a syntax error.

 
 
[js]


```js
/(?<name>)(?<name>)/; // SyntaxError: Invalid regular expression: Duplicate capture group name
```


This restriction is relaxed if the duplicate named capturing groups are
not in the same [disjunction alternative](disjunction), so for any
string input, only one named capturing group can actually be matched.
This is a much newer feature, so check [browser
compatibility](#browser_compatibility) before using it.

 
 
[js]


```js
/(?<year>\d{4})-\d{2}|\d{2}-(?<year>\d{4})/;
// Works; "year" can either come before or after the hyphen
```


Named capturing groups will all be present in the result. If a named
capturing group is not matched (for example, it belongs to an unmatched
alternative in a [disjunction](disjunction)), the corresponding property
on the `groups` object has value `undefined`.

 
 
[js]


```js
/(?<ab>ab)|(?<cd>cd)/.exec("cd").groups; // [Object: null prototype] { ab: undefined, cd: 'cd' }
```


You can get the start and end indices of each named capturing group in
the input string by using the [`d`](../global_objects/regexp/hasindices)
flag. In addition to accessing them on the `indices` property on the
array returned by `exec()`, you can also access them by their names on
`indices.groups`.

Compared to unnamed capturing groups, named capturing groups have the
following advantages:

-   They allow you to provide a descriptive name for each submatch
    result.
-   They allow you to access submatch results without having to remember
    the order in which they appear in the pattern.
-   When refactoring code, you can change the order of capturing groups
    without worrying about breaking other references.



 
Examples
--------


 
### Using named capturing groups 

 
The following example parses a timestamp and an author name from a Git
log entry (output with `git log --format=%ct,%an -- filename`):

 
 
[js]


```js
function parseLog(entry) {
  const { author, timestamp } = /^(?<timestamp>\d+),(?<author>.+)$/.exec(
    entry,
  ).groups;
  return `${author} committed on ${new Date(
    parseInt(timestamp) * 1000,
  ).toLocaleString()}`;
}

parseLog("1560979912,Caroline"); // "Caroline committed on 6/19/2019, 5:31:52 PM"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  prod-Atom]](https://tc39.es/ecma262/multipage/text-processing.html#prod-Atom)

  ---------------------------------------------------------------------------------------


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

`Named_capturing_group`

64

79

78

51

11.1

64

79

47

11.3

9.0

64

1.0

10.0.0

`duplicate_named_capturing_groups`

No

No

No

No

preview

No

No

No

No

No

No

No

No

 
See also 
--------

 
-   [Polyfill of named capturing groups in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [Groups and
    backreferences](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions/Groups_and_backreferences)
    guide
-   [Regular expressions](../regular_expressions)
-   [Capturing group: `(...)`](capturing_group)
-   [Non-capturing group: `(?:...)`](non-capturing_group)
-   [Named backreference: `\k<name>`](named_backreference)
-   [ESLint rule:
    `prefer-named-capture-group`](https://eslint.org/docs/rules/prefer-named-capture-group)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Named_capturing_group>

