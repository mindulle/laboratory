unescape()
==========

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


 
**Note:** `unescape()` is a non-standard function implemented by
browsers and was only standardized for cross-engine compatibility. It is
not required to be implemented by all JavaScript engines and may not
work everywhere. Use [`decodeURIComponent()`](decodeuricomponent) or
[`decodeURI()`](decodeuri) if possible.


The `unescape()` function computes a new string in which hexadecimal
escape sequences are replaced with the characters that they represent.
The escape sequences might be introduced by a function like
[`escape()`](escape).


 
Syntax
------

 
 
 
[js]


```js
unescape(str)
```




 
### Parameters

 

[`str`](#str)

:   A string to be decoded.



 
### Return value 

 
A new string in which certain characters have been unescaped.



 
Description
-----------

 
`unescape()` is a function property of the global object.

The `unescape()` function replaces any escape sequence with the
character that it represents. Specifically, it replaces any escape
sequence of the form `%XX` or `%uXXXX` (where `X` represents one
hexadecimal digit) with the character that has the hexadecimal value
`XX`/`XXXX`. If the escape sequence is not a valid escape sequence (for
example, if `%` is followed by one or no hex digit), it is left as-is.

 
**Note:** This function was used mostly for [URL
encoding](https://en.wikipedia.org/wiki/URL_encoding) and is partly
based on the escape format in [RFC
1738](https://datatracker.ietf.org/doc/html/rfc1738). The `unescape()`
function does *not* evaluate [escape
sequences](../lexical_grammar#escape_sequences) in string literals. You
can replace `\xXX` with `%XX` and `\uXXXX` with `%uXXXX` to get a string
that can be handled by `unescape()`.




 
Examples
--------


 
### Using unescape() 

 
 
 
[js]


```js
unescape("abc123"); // "abc123"
unescape("%E4%F6%FC"); // "äöü"
unescape("%u0107"); // "ć"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-unescape-string]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#sec-unescape-string)

  -------------------------------------------------------------------------------------------------------------------------------------------


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

`unescape`

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

 
-   [Polyfill of `unescape` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`decodeURI`](decodeuri)
-   [`decodeURIComponent`](decodeuricomponent)
-   [`escape`](escape)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/unescape>

