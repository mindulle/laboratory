String.prototype.charAt()
=========================

 
The `charAt()` method of [`String`](../string) values returns a new
string consisting of the single UTF-16 code unit at the given index.

`charAt()` always indexes the string as a sequence of [UTF-16 code
units](../string#utf-16_characters_unicode_code_points_and_grapheme_clusters),
so it may return lone surrogates. To get the full Unicode code point at
the given index, use [`String.prototype.codePointAt()`](codepointat) and
[`String.fromCodePoint()`](fromcodepoint).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
charAt(index)
```




 
### Parameters

 

[`index`](#index)

:   Zero-based index of the character to be returned. [Converted to an
    integer](../number#integer_conversion) --- `undefined` is converted
    to 0.



 
### Return value 

 
A string representing the character (exactly one UTF-16 code unit) at
the specified `index`. If `index` is out of the range of `0` --
`str.length - 1`, `charAt()` returns an empty string.



 
Description
-----------

 
Characters in a string are indexed from left to right. The index of the
first character is `0`, and the index of the last character in a string
called `str` is `str.length - 1`.

Unicode code points range from `0` to `1114111` (`0x10FFFF`). `charAt()`
always returns a character whose value is less than `65536`, because the
higher code points are represented by *a pair* of 16-bit surrogate
pseudo-characters. Therefore, in order to get a full character with
value greater than `65535`, it is necessary to retrieve not only
`charAt(i)`, but also `charAt(i + 1)` (as if manipulating a string with
two characters), or to use [`codePointAt(i)`](codepointat) and
[`String.fromCodePoint()`](fromcodepoint) instead. For information on
Unicode, see [UTF-16 characters, Unicode code points, and grapheme
clusters](../string#utf-16_characters_unicode_code_points_and_grapheme_clusters).

`charAt()` is very similar to using [bracket
notation](../../operators/property_accessors#bracket_notation) to access
a character at the specified index. The main differences are:

-   `charAt()` attempts to convert `index` to an integer, while bracket
    notation does not, and directly uses `index` as a property name.
-   `charAt()` returns an empty string if `index` is out of range, while
    bracket notation returns `undefined`.



 
Examples
--------


 
### Using charAt() 

 
The following example displays characters at different locations in the
string `"Brave new world"`:

 
 
[js]


```js
const anyString = "Brave new world";
console.log(`The character at index 0   is '${anyString.charAt()}'`);
// No index was provided, used 0 as default

console.log(`The character at index 0   is '${anyString.charAt(0)}'`);
console.log(`The character at index 1   is '${anyString.charAt(1)}'`);
console.log(`The character at index 2   is '${anyString.charAt(2)}'`);
console.log(`The character at index 3   is '${anyString.charAt(3)}'`);
console.log(`The character at index 4   is '${anyString.charAt(4)}'`);
console.log(`The character at index 999 is '${anyString.charAt(999)}'`);
```


These lines display the following:

```text
The character at index 0   is 'B'

The character at index 0   is 'B'
The character at index 1   is 'r'
The character at index 2   is 'a'
The character at index 3   is 'v'
The character at index 4   is 'e'
The character at index 999 is ''
```

`charAt()` may return lone surrogates, which are not valid Unicode
characters.

 
 
[js]


```js
const str = "𠮷𠮾";
console.log(str.charAt(0)); // "\ud842", which is not a valid Unicode character
console.log(str.charAt(1)); // "\udfb7", which is not a valid Unicode character
```


To get the full Unicode code point at the given index, use an indexing
method that splits by Unicode code points, such as
[`String.prototype.codePointAt()`](codepointat) and [spreading
strings](@@iterator) into an array of Unicode code points.

 
 
[js]


```js
const str = "𠮷𠮾";
console.log(String.fromCodePoint(str.codePointAt(0))); // "𠮷"
console.log([...str][0]); // "𠮷"
```


 
**Note:** Avoid re-implementing the solutions above using `charAt()`.
The detection of lone surrogates and their pairing is complex, and
built-in APIs may be more performant as they directly use the internal
representation of the string. Install a polyfill for the APIs mentioned
above if necessary.




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.charat]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.charat)

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

`charAt`

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

 
-   [`String.prototype.indexOf()`](indexof)
-   [`String.prototype.lastIndexOf()`](lastindexof)
-   [`String.prototype.charCodeAt()`](charcodeat)
-   [`String.prototype.codePointAt()`](codepointat)
-   [`String.prototype.split()`](split)
-   [`String.fromCodePoint()`](fromcodepoint)
-   [JavaScript has a Unicode
    problem](https://mathiasbynens.be/notes/javascript-unicode) by
    Mathias Bynens (2013)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charAt>

