String.prototype.lastIndexOf()
==============================

 
The `lastIndexOf()` method of [`String`](../string) values searches this
string and returns the index of the last occurrence of the specified
substring. It takes an optional starting position and returns the last
occurrence of the specified substring at an index less than or equal to
the specified number.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
lastIndexOf(searchString)
lastIndexOf(searchString, position)
```




 
### Parameters

 

[`searchString`](#searchstring)

:   Substring to search for. All values are [coerced to
    strings](../string#string_coercion), so omitting it or passing
    `undefined` causes `lastIndexOf()` to search for the string
    `"undefined"`, which is rarely what you want.

[`position`](#position) [Optional]

:   The method returns the index of the last occurrence of the specified
    substring at a position less than or equal to `position`, which
    defaults to `+Infinity`. If `position` is greater than the length of
    the calling string, the method searches the entire string. If
    `position` is less than `0`, the behavior is the same as for `0` ---
    that is, the method looks for the specified substring only at index
    `0`.

    -   `'hello world hello'.lastIndexOf('world', 4)` returns `-1` ---
        because, while the substring `world` does occurs at index `6`,
        that position is not less than or equal to `4`.
    -   `'hello world hello'.lastIndexOf('hello', 99)` returns `12` ---
        because the last occurrence of `hello` at a position less than
        or equal to `99` is at position `12`.
    -   `'hello world hello'.lastIndexOf('hello', 0)` and
        `'hello world hello'.lastIndexOf('hello', -5)` both return `0`
        --- because both cause the method to only look for `hello` at
        index `0`.



 
### Return value 

 
The index of the last occurrence of `searchString` found, or `-1` if not
found.



 
Description
-----------

 
Strings are zero-indexed: The index of a string\'s first character is
`0`, and the index of a string\'s last character is the length of the
string minus 1.

 
 
[js]


```js
"canal".lastIndexOf("a"); // returns 3
"canal".lastIndexOf("a", 2); // returns 1
"canal".lastIndexOf("a", 0); // returns -1
"canal".lastIndexOf("x"); // returns -1
"canal".lastIndexOf("c", -5); // returns 0
"canal".lastIndexOf("c", 0); // returns 0
"canal".lastIndexOf(""); // returns 5
"canal".lastIndexOf("", 2); // returns 2
```




 
### Case-sensitivity

 
The `lastIndexOf()` method is case sensitive. For example, the following
expression returns `-1`:

 
 
[js]


```js
"Blue Whale, Killer Whale".lastIndexOf("blue"); // returns -1
```




 
Examples
--------


 
### Using indexOf() and lastIndexOf() 

 
The following example uses [`indexOf()`](indexof) and `lastIndexOf()` to
locate values in the string `"Brave, Brave New World"`.

 
 
[js]


```js
const anyString = "Brave, Brave New World";

console.log(anyString.indexOf("Brave")); // 0
console.log(anyString.lastIndexOf("Brave")); // 7
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.lastindexof]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.lastindexof)

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

`lastIndexOf`

1

12

1

3

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

 
-   [`String.prototype.charAt()`](charat)
-   [`String.prototype.indexOf()`](indexof)
-   [`String.prototype.split()`](split)
-   [`Array.prototype.indexOf()`](../array/indexof)
-   [`Array.prototype.lastIndexOf()`](../array/lastindexof)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/lastIndexOf>

