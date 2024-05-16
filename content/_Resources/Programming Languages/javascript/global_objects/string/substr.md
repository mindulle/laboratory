String.prototype.substr()
=========================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


The `substr()` method of [`String`](../string) values returns a portion
of this string, starting at the specified index and extending for a
given number of characters afterwards.

 
**Note:** `substr()` is not part of the main ECMAScript specification
--- it\'s defined in [Annex B: Additional ECMAScript Features for Web
Browsers](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html),
which is normative optional for non-browser runtimes. Therefore, people
are advised to use the standard
[`String.prototype.substring()`](substring) and
[`String.prototype.slice()`](slice) methods instead to make their code
maximally cross-platform friendly. The [`String.prototype.substring()`
page](substring#the_difference_between_substring_and_substr) has some
comparisons between the three methods.



 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
substr(start)
substr(start, length)
```




 
### Parameters

 

[`start`](#start)

:   The index of the first character to include in the returned
    substring.

[`length`](#length) [Optional]

:   The number of characters to extract.



 
### Return value 

 
A new string containing the specified part of the given string.



 
Description
-----------

 
A string\'s `substr()` method extracts `length` characters from the
string, counting from the `start` index.

-   If `start >= str.length`, an empty string is returned.
-   If `start < 0`, the index starts counting from the end of the
    string. More formally, in this case the substring starts at
    `max(start + str.length, 0)`.
-   If `start` is omitted or [`undefined`](../undefined), it\'s treated
    as `0`.
-   If `length` is omitted or [`undefined`](../undefined), or if
    `start + length >= str.length`, `substr()` extracts characters to
    the end of the string.
-   If `length < 0`, an empty string is returned.
-   For both `start` and `length`, [`NaN`](../nan) is treated as `0`.

Although you are encouraged to avoid using `substr()`, there is no
trivial way to migrate `substr()` to either `slice()` or `substring()`
in legacy code without essentially writing a polyfill for `substr()`.
For example, `str.substr(a, l)`, `str.slice(a, a + l)`, and
`str.substring(a, a + l)` all have different results when
`str = "01234", a = 1, l = -2` --- `substr()` returns an empty string,
`slice()` returns `"123"`, while `substring()` returns `"0"`. The actual
refactoring path depends on the knowledge of the range of `a` and `l`.



 
Examples
--------


 
### Using substr() 

 
 
 
[js]


```js
const aString = "Mozilla";

console.log(aString.substr(0, 1)); // 'M'
console.log(aString.substr(1, 0)); // ''
console.log(aString.substr(-1, 1)); // 'a'
console.log(aString.substr(1, -1)); // ''
console.log(aString.substr(-3)); // 'lla'
console.log(aString.substr(1)); // 'ozilla'
console.log(aString.substr(-20, 2)); // 'Mo'
console.log(aString.substr(20, 2)); // ''
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.substr]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#sec-string.prototype.substr)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------


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

`substr`

1

12

1

4

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

 
-   [Polyfill of `String.prototype.substr` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.prototype.slice()`](slice)
-   [`String.prototype.substring()`](substring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substr>

