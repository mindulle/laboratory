encodeURI()
===========

 
The `encodeURI()` function encodes a
[URI](https://developer.mozilla.org/en-US/docs/Glossary/URI) by
replacing each instance of certain characters by one, two, three, or
four escape sequences representing the
[UTF-8](https://developer.mozilla.org/en-US/docs/Glossary/UTF-8)
encoding of the character (will only be four escape sequences for
characters composed of two surrogate characters). Compared to
[`encodeURIComponent()`](encodeuricomponent), this function encodes
fewer characters, preserving those that are part of the URI syntax.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
encodeURI(uri)
```




 
### Parameters

 

[`uri`](#uri)

:   A string to be encoded as a URI.



 
### Return value 

 
A new string representing the provided string encoded as a URI.



 
### Exceptions

 

[`URIError`](urierror)

:   Thrown if `uri` contains a [lone
    surrogate](string#utf-16_characters_unicode_code_points_and_grapheme_clusters).



 
Description
-----------

 
`encodeURI()` is a function property of the global object.

The `encodeURI()` function escapes characters by UTF-8 code units, with
each octet encoded in the format `%XX`, left-padded with 0 if necessary.
Because lone surrogates in UTF-16 do not encode any valid Unicode
character, they cause `encodeURI()` to throw a [`URIError`](urierror).

`encodeURI()` escapes all characters **except**:

```text
A–Z a–z 0–9 - _ . ! ~ * ' ( )

; / ? : @ & = + $ , #
```

The characters on the second line are characters that may be part of the
URI syntax, and are only escaped by `encodeURIComponent()`. Both
`encodeURI()` and `encodeURIComponent()` do not encode the characters
`-.!~*'()`, known as \"unreserved marks\", which do not have a reserved
purpose but are allowed in a URI \"as is\". (See
[RFC2396](https://www.ietf.org/rfc/rfc2396.txt))

The `encodeURI()` function does not encode characters that have special
meaning (reserved characters) for a URI. The following example shows all
the parts that a URI can possibly contain. Note how certain characters
are used to signify special meaning:

 
 
[url]


```url
http://username:password@www.example.com:80/path/to/file.php?foo=316&bar=this+has+spaces#anchor
```


`encodeURI`, as the name implies, is used to encode a URL as a whole,
assuming it is already well-formed. If you want to dynamically assemble
string values into a URL, you probably want to use
[`encodeURIComponent()`](encodeuricomponent) on each dynamic segment
instead, to avoid URL syntax characters in unwanted places.

 
 
[js]


```js
const name = "Ben & Jerry's";

// This is bad:
const link = encodeURI(`https://example.com/?choice=${name}`); // "https://example.com/?choice=Ben%20&%20Jerry's"
console.log([...new URL(link).searchParams]); // [['choice', 'Ben '], [" Jerry's", '']

// Instead:
const link = encodeURI(
  `https://example.com/?choice=${encodeURIComponent(name)}`,
);
// "https://example.com/?choice=Ben%2520%2526%2520Jerry's"
console.log([...new URL(link).searchParams]); // [['choice', "Ben%20%26%20Jerry's"]]
```




 
Examples
--------


 
### encodeURI() vs. encodeURIComponent() 

 
`encodeURI()` differs from [`encodeURIComponent()`](encodeuricomponent)
as follows:

 
 
[js]


```js
const set1 = ";/?:@&=+$,#"; // Reserved Characters
const set2 = "-.!~*'()"; // Unreserved Marks
const set3 = "ABC abc 123"; // Alphanumeric Characters + Space

console.log(encodeURI(set1)); // ;/?:@&=+$,#
console.log(encodeURI(set2)); // -.!~*'()
console.log(encodeURI(set3)); // ABC%20abc%20123 (the space gets encoded as %20)

console.log(encodeURIComponent(set1)); // %3B%2C%2F%3F%3A%40%26%3D%2B%24%23
console.log(encodeURIComponent(set2)); // -.!~*'()
console.log(encodeURIComponent(set3)); // ABC%20abc%20123 (the space gets encoded as %20)
```




 
### Encoding a lone surrogate throws 

 
A [`URIError`](urierror) will be thrown if one attempts to encode a
surrogate which is not part of a high-low pair. For example:

 
 
[js]


```js
// High-low pair OK
encodeURI("\uD800\uDFFF"); // "%F0%90%8F%BF"

// Lone high-surrogate code unit throws "URIError: malformed URI sequence"
encodeURI("\uD800");

// Lone low-surrogate code unit throws "URIError: malformed URI sequence"
encodeURI("\uDFFF");
```


You can use [`String.prototype.toWellFormed()`](string/towellformed),
which replaces lone surrogates with the Unicode replacement character
(U+FFFD), to avoid this error. You can also use
[`String.prototype.isWellFormed()`](string/iswellformed) to check if a
string contains lone surrogates before passing it to `encodeURI()`.



 
### Encoding for RFC3986 

 
The more recent [RFC3986](https://datatracker.ietf.org/doc/html/rfc3986)
makes square brackets reserved (for
[IPv6](https://developer.mozilla.org/en-US/docs/Glossary/IPv6)) and thus
not encoded when forming something which could be part of a URL (such as
a host). It also reserves !, \', (, ), and \*, even though these
characters have no formalized URI delimiting uses. The following
function encodes a string for RFC3986-compliant URL format.

 
 
[js]


```js
function encodeRFC3986URI(str) {
  return encodeURI(str)
    .replace(/%5B/g, "[")
    .replace(/%5D/g, "]")
    .replace(
      /[!'()*]/g,
      (c) => `%${c.charCodeAt(0).toString(16).toUpperCase()}`,
    );
}
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-encodeuri-uri]](https://tc39.es/ecma262/multipage/global-object.html#sec-encodeuri-uri)

  -----------------------------------------------------------------------------------------------------


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

`encodeURI`

1

12

1

7

1.1

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

 
-   [`decodeURI()`](decodeuri)
-   [`encodeURIComponent()`](encodeuricomponent)
-   [`decodeURIComponent()`](decodeuricomponent)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURI>

