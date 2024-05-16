RegExp.prototype.test()
=======================

 
The `test()` method of [`RegExp`](../regexp) instances executes a search
with this regular expression for a match between a regular expression
and a specified string. Returns `true` if there is a match; `false`
otherwise.

JavaScript [`RegExp`](../regexp) objects are **stateful** when they have
the [`global`](global) or [`sticky`](sticky) flags set (e.g., `/foo/g`
or `/foo/y`). They store a [`lastIndex`](lastindex) from the previous
match. Using this internally, `test()` can be used to iterate over
multiple matches in a string of text (with capture groups).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
test(str)
```




 
### Parameters

 

[`str`](#str)

:   The string against which to match the regular expression. All values
    are [coerced to strings](../string#string_coercion), so omitting it
    or passing `undefined` causes `test()` to search for the string
    `"undefined"`, which is rarely what you want.



 
### Return value 

 
`true` if there is a match between the regular expression and the string
`str`. Otherwise, `false`.



 
Description
-----------

 
Use `test()` whenever you want to know whether a pattern is found in a
string. `test()` returns a boolean, unlike the
[`String.prototype.search()`](../string/search) method (which returns
the index of a match, or `-1` if not found).

To get more information (but with slower execution), use the
[`exec()`](exec) method. (This is similar to the
[`String.prototype.match()`](../string/match) method.)

As with `exec()` (or in combination with it), `test()` called multiple
times on the same global regular expression instance will advance past
the previous match.



 
Examples
--------


 
### Using test() 

 
Simple example that tests if `"hello"` is contained at the very
beginning of a string, returning a boolean result.

 
 
[js]


```js
const str = "hello world!";
const result = /^hello/.test(str);

console.log(result); // true
```


The following example logs a message which depends on the success of the
test:

 
 
[js]


```js
function testInput(re, str) {
  const midstring = re.test(str) ? "contains" : "does not contain";
  console.log(`${str}${midstring}${re.source}`);
}
```




 
### Using test() on a regex with the \"global\" flag 

 
When a regex has the [global flag](global) set, `test()` will advance
the [`lastIndex`](lastindex) of the regex.
([`RegExp.prototype.exec()`](exec) also advances the `lastIndex`
property.)

Further calls to `test(str)` will resume searching `str` starting from
`lastIndex`. The `lastIndex` property will continue to increase each
time `test()` returns `true`.

 
**Note:** As long as `test()` returns `true`, `lastIndex` will *not*
reset---even when testing a different string!


When `test()` returns `false`, the calling regex\'s `lastIndex` property
will reset to `0`.

The following example demonstrates this behavior:

 
 
[js]


```js
const regex = /foo/g; // the "global" flag is set

// regex.lastIndex is at 0
regex.test("foo"); // true

// regex.lastIndex is now at 3
regex.test("foo"); // false

// regex.lastIndex is at 0
regex.test("barfoo"); // true

// regex.lastIndex is at 6
regex.test("foobar"); // false

// regex.lastIndex is at 0
regex.test("foobarfoo"); // true

// regex.lastIndex is at 3
regex.test("foobarfoo"); // true

// regex.lastIndex is at 9
regex.test("foobarfoo"); // false

// regex.lastIndex is at 0
// (...and so on)
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-regexp.prototype.test]](https://tc39.es/ecma262/multipage/text-processing.html#sec-regexp.prototype.test)

  -----------------------------------------------------------------------------------------------------------------------


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

`test`

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

 
-   [Regular
    expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions)
    guide
-   [`RegExp`](../regexp)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/test>

