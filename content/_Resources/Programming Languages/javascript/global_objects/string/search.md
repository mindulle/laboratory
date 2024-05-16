String.prototype.search()
=========================

 
The `search()` method of [`String`](../string) values executes a search
for a match between a regular expression and this string, returning the
index of the first match in the string.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
search(regexp)
```




 
### Parameters

 

[`regexp`](#regexp)

:   A regular expression object, or any object that has a
    [`Symbol.search`](../symbol/search) method.

    If `regexp` is not a `RegExp` object and does not have a
    `Symbol.search` method, it is implicitly converted to a
    [`RegExp`](../regexp) by using `new RegExp(regexp)`.



 
### Return value 

 
The index of the first match between the regular expression and the
given string, or `-1` if no match was found.



 
Description
-----------

 
The implementation of `String.prototype.search()` itself is very simple
--- it simply calls the `Symbol.search` method of the argument with the
string as the first parameter. The actual implementation comes from
[`RegExp.prototype[@@search]()`](../regexp/@@search).

The `g` flag of `regexp` has no effect on the `search()` result, and the
search always happens as if the regex\'s `lastIndex` is 0. For more
information on the behavior of `search()`, see
[`RegExp.prototype[@@search]()`](../regexp/@@search).

When you want to know whether a pattern is found, and *also* know its
index within a string, use `search()`.

-   If you only want to know if it exists, use the
    [`RegExp.prototype.test()`](../regexp/test) method, which returns a
    boolean.
-   If you need the content of the matched text, use
    [`String.prototype.match()`](match) or
    [`RegExp.prototype.exec()`](../regexp/exec).



 
Examples
--------


 
### Using search() 

 
The following example searches a string with two different regex objects
to show a successful search (positive value) vs. an unsuccessful search
(`-1`).

 
 
[js]


```js
const str = "hey JudE";
const re = /[A-Z]/;
const reDot = /[.]/;
console.log(str.search(re)); // returns 4, which is the index of the first capital letter "J"
console.log(str.search(reDot)); // returns -1 cannot find '.' dot punctuation
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.search]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.search)

  ---------------------------------------------------------------------------------------------------------------------------


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

`search`

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

 
-   [Polyfill of `String.prototype.search` in `core-js` with fixes and
    implementation of modern behavior like `Symbol.search`
    support](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [Regular
    expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions)
    guide
-   [`String.prototype.match()`](match)
-   [`RegExp.prototype.exec()`](../regexp/exec)
-   [`RegExp.prototype[@@search]()`](../regexp/@@search)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/search>

