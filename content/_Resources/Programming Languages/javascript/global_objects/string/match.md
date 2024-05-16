String.prototype.match()
========================

 
The `match()` method of [`String`](../string) values retrieves the
result of matching this string against a [regular
expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
match(regexp)
```




 
### Parameters

 

[`regexp`](#regexp)

:   A regular expression object, or any object that has a
    [`Symbol.match`](../symbol/match) method.

    If `regexp` is not a `RegExp` object and does not have a
    `Symbol.match` method, it is implicitly converted to a
    [`RegExp`](../regexp) by using `new RegExp(regexp)`.

    If you don\'t give any parameter and use the `match()` method
    directly, you will get an [`Array`](../array) with an empty string:
    `[""]`, because this is equivalent to `match(/(?:)/)`.



 
### Return value 

 
An [`Array`](../array) whose contents depend on the presence or absence
of the global (`g`) flag, or [`null`](../../operators/null) if no
matches are found.

-   If the `g` flag is used, all results matching the complete regular
    expression will be returned, but capturing groups are not included.
-   If the `g` flag is not used, only the first complete match and its
    related capturing groups are returned. In this case, `match()` will
    return the same result as
    [`RegExp.prototype.exec()`](../regexp/exec) (an array with some
    extra properties).



 
Description
-----------

 
The implementation of `String.prototype.match` itself is very simple ---
it simply calls the `Symbol.match` method of the argument with the
string as the first parameter. The actual implementation comes from
[`RegExp.prototype[@@match]()`](../regexp/@@match).

-   If you need to know if a string matches a regular expression
    [`RegExp`](../regexp), use
    [`RegExp.prototype.test()`](../regexp/test).
-   If you only want the first match found, you might want to use
    [`RegExp.prototype.exec()`](../regexp/exec) instead.
-   If you want to obtain capture groups and the global flag is set, you
    need to use [`RegExp.prototype.exec()`](../regexp/exec) or
    [`String.prototype.matchAll()`](matchall) instead.

For more information about the semantics of `match()` when a regex is
passed, see [`RegExp.prototype[@@match]()`](../regexp/@@match).



 
Examples
--------


 
### Using match() 

 
In the following example, `match()` is used to find `"Chapter"` followed
by one or more numeric characters followed by a decimal point and
numeric character zero or more times.

The regular expression includes the `i` flag so that upper/lower case
differences will be ignored.

 
 
[js]


```js
const str = "For more information, see Chapter 3.4.5.1";
const re = /see (chapter \d+(\.\d)*)/i;
const found = str.match(re);

console.log(found);
// [
//   'see Chapter 3.4.5.1',
//   'Chapter 3.4.5.1',
//   '.1',
//   index: 22,
//   input: 'For more information, see Chapter 3.4.5.1',
//   groups: undefined
// ]
```


In the match result above, `'see Chapter 3.4.5.1'` is the whole match.
`'Chapter 3.4.5.1'` was captured by `(chapter \d+(\.\d)*)`. `'.1'` was
the last value captured by `(\.\d)`. The `index` property (`22`) is the
zero-based index of the whole match. The `input` property is the
original string that was parsed.



 
### Using global and ignoreCase flags with match() 

 
The following example demonstrates the use of the global flag and
ignore-case flag with `match()`. All letters `A` through `E` and `a`
through `e` are returned, each its own element in the array.

 
 
[js]


```js
const str = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz";
const regexp = /[A-E]/gi;
const matches = str.match(regexp);

console.log(matches);
// ['A', 'B', 'C', 'D', 'E', 'a', 'b', 'c', 'd', 'e']
```


 
**Note:** See also [`String.prototype.matchAll()`](matchall) and
[Advanced searching with
flags](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions#advanced_searching_with_flags).




 
### Using named capturing groups 

 
In browsers which support named capturing groups, the following code
captures `"fox"` or `"cat"` into a group named `animal`:

 
 
[js]


```js
const paragraph = "The quick brown fox jumps over the lazy dog. It barked.";

const capturingRegex = /(?<animal>fox|cat) jumps over/;
const found = paragraph.match(capturingRegex);
console.log(found.groups); // {animal: "fox"}
```




 
### Using match() with no parameter 

 
 
 
[js]


```js
const str = "Nothing will come of nothing.";

str.match(); // returns [""]
```




 
### Using match() with a non-RegExp implementing @\@match 

 
If an object has a `Symbol.match` method, it can be used as a custom
matcher. The return value of `Symbol.match` becomes the return value of
`match()`.

 
 
[js]


```js
const str = "Hmm, this is interesting.";

str.match({
  [Symbol.match](str) {
    return ["Yes, it's interesting."];
  },
}); // returns ["Yes, it's interesting."]
```




 
### A non-RegExp as the parameter 

 
When the `regexp` parameter is a string or a number, it is implicitly
converted to a [`RegExp`](../regexp) by using `new RegExp(regexp)`.

 
 
[js]


```js
const str1 =
  "NaN means not a number. Infinity contains -Infinity and +Infinity in JavaScript.";
const str2 =
  "My grandfather is 65 years old and My grandmother is 63 years old.";
const str3 = "The contract was declared null and void.";
str1.match("number"); // "number" is a string. returns ["number"]
str1.match(NaN); // the type of NaN is the number. returns ["NaN"]
str1.match(Infinity); // the type of Infinity is the number. returns ["Infinity"]
str1.match(+Infinity); // returns ["Infinity"]
str1.match(-Infinity); // returns ["-Infinity"]
str2.match(65); // returns ["65"]
str2.match(+65); // A number with a positive sign. returns ["65"]
str3.match(null); // returns ["null"]
```


This may have unexpected results if special characters are not properly
escaped.

 
 
[js]


```js
console.log("123".match("1.3")); // [ "123" ]
```


This is a match because `.` in a regex matches any character. In order
to make it only match specifically a dot character, you need to escape
the input.

 
 
[js]


```js
console.log("123".match("1\\.3")); // null
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.match]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.match)

  -------------------------------------------------------------------------------------------------------------------------


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

`match`

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

 
-   [Polyfill of `String.prototype.match` in `core-js` with fixes and
    implementation of modern behavior like `Symbol.match`
    support](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.prototype.matchAll()`](matchall)
-   [`RegExp`](../regexp)
-   [`RegExp.prototype.exec()`](../regexp/exec)
-   [`RegExp.prototype.test()`](../regexp/test)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match>

