String.prototype.replaceAll()
=============================

 
The `replaceAll()` method of [`String`](../string) values returns a new
string with all matches of a `pattern` replaced by a `replacement`. The
`pattern` can be a string or a [`RegExp`](../regexp), and the
`replacement` can be a string or a function to be called for each match.
The original string is left unchanged.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
replaceAll(pattern, replacement)
```




 
### Parameters

 

[`pattern`](#pattern)

:   Can be a string or an object with a
    [`Symbol.replace`](../symbol/replace) method --- the typical example
    being a [regular expression](../regexp). Any value that doesn\'t
    have the `Symbol.replace` method will be coerced to a string.

    If `pattern` [is a regex](../regexp#special_handling_for_regexes),
    then it must have the global (`g`) flag set, or a
    [`TypeError`](../typeerror) is thrown.

[`replacement`](#replacement)

:   Can be a string or a function. The replacement has the same
    semantics as that of [`String.prototype.replace()`](replace).



 
### Return value 

 
A new string, with all matches of a pattern replaced by a replacement.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if the `pattern` [is a
    regex](../regexp#special_handling_for_regexes) that does not have
    the global (`g`) flag set (its [`flags`](../regexp/flags) property
    does not contain `"g"`).



 
Description
-----------

 
This method does not mutate the string value it\'s called on. It returns
a new string.

Unlike [`replace()`](replace), this method would replace all occurrences
of a string, not just the first one. This is especially useful if the
string is not statically known, as calling the
[`RegExp()`](../regexp/regexp) constructor without escaping special
characters may unintentionally change its semantics.

 
 
[js]


```js
function unsafeRedactName(text, name) {
  return text.replace(new RegExp(name, "g"), "[REDACTED]");
}
function safeRedactName(text, name) {
  return text.replaceAll(name, "[REDACTED]");
}

const report =
  "A hacker called ha.*er used special characters in their name to breach the system.";

console.log(unsafeRedactName(report, "ha.*er")); // "A [REDACTED]s in their name to breach the system."
console.log(safeRedactName(report, "ha.*er")); // "A hacker called [REDACTED] used special characters in their name to breach the system."
```


If `pattern` is an object with a [`Symbol.replace`](../symbol/replace)
method (including `RegExp` objects), that method is called with the
target string and `replacement` as arguments. Its return value becomes
the return value of `replaceAll()`. In this case the behavior of
`replaceAll()` is entirely encoded by the `@@replace` method, and
therefore will have the same result as `replace()` (apart from the extra
input validation that the regex is global).

If the `pattern` is an empty string, the replacement will be inserted in
between every UTF-16 code unit, similar to [`split()`](split) behavior.

 
 
[js]


```js
"xxx".replaceAll("", "_"); // "_x_x_x_"
```


For more information about how regex properties (especially the
[sticky](../regexp/sticky) flag) interact with `replaceAll()`, see
[`RegExp.prototype[@@replace]()`](../regexp/@@replace).



 
Examples
--------


 
### Using replaceAll() 

 
 
 
[js]


```js
"aabbcc".replaceAll("b", ".");
// 'aa..cc'
```




 
### Non-global regex throws 

 
When using a regular expression search value, it must be global. This
won\'t work:

 
 
[js]


```js
"aabbcc".replaceAll(/b/, ".");
// TypeError: replaceAll must be called with a global RegExp
```


This will work:

 
 
[js]


```js
"aabbcc".replaceAll(/b/g, ".");
("aa..cc");
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.replaceall]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.replaceall)

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

`replaceAll`

85

85

77

71

13.1

85

79

60

13.4

14.0

85

1.2

15.0.0

 
See also 
--------

 
-   [Polyfill of `String.prototype.replaceAll` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.prototype.replace()`](replace)
-   [`String.prototype.match()`](match)
-   [`RegExp.prototype.exec()`](../regexp/exec)
-   [`RegExp.prototype.test()`](../regexp/test)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replaceAll>

