decodeURI()
===========

 
The `decodeURI()` function decodes a Uniform Resource Identifier (URI)
previously created by [`encodeURI()`](encodeuri) or a similar routine.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
decodeURI(encodedURI)
```




 
### Parameters

 

[`encodedURI`](#encodeduri)

:   A complete, encoded Uniform Resource Identifier.



 
### Return value 

 
A new string representing the unencoded version of the given encoded
Uniform Resource Identifier (URI).



 
### Exceptions

 

[`URIError`](urierror)

:   Thrown if `encodedURI` contains a `%` not followed by two
    hexadecimal digits, or if the escape sequence does not encode a
    valid UTF-8 character.



 
Description
-----------

 
`decodeURI()` is a function property of the global object.

The `decodeURI()` function decodes the URI by treating each escape
sequence in the form `%XX` as one UTF-8 code unit (one byte). In UTF-8,
the number of leading 1 bits in the first byte, which may be 0 (for
1-byte [ASCII](https://developer.mozilla.org/en-US/docs/Glossary/ASCII)
characters), 2, 3, or 4, indicates the number of bytes in the character.
So by reading the first escape sequence, `decodeURI()` can determine how
many more escape sequences to consume. If `decodeURI()` fails to find
the expected number of sequences, or if the escape sequences don\'t
encode a valid UTF-8 character, a [`URIError`](urierror) is thrown.

`decodeURI()` decodes all escape sequences, but if the escape sequence
encodes one of the following characters, the escape sequence is
preserved in the output string (because they are part of the URI
syntax):

```text
; / ? : @ & = + $ , #
```



 
Examples
--------


 
### Decoding a Cyrillic URL 

 
 
 
[js]


```js
decodeURI(
  "https://developer.mozilla.org/ru/docs/JavaScript_%D1%88%D0%B5%D0%BB%D0%BB%D1%8B",
);
// "https://developer.mozilla.org/ru/docs/JavaScript_шеллы"
```




 
### decodeURI() vs. decodeURIComponent() 

 
`decodeURI()` assumes the input is a full URI, so it does not decode
characters that are part of the URI syntax.

 
 
[js]


```js
decodeURI(
  "https://developer.mozilla.org/docs/JavaScript%3A%20a_scripting_language",
);
// "https://developer.mozilla.org/docs/JavaScript%3A a_scripting_language"

decodeURIComponent(
  "https://developer.mozilla.org/docs/JavaScript%3A%20a_scripting_language",
);
// "https://developer.mozilla.org/docs/JavaScript: a_scripting_language"
```




 
### Catching errors 

 
 
 
[js]


```js
try {
  const a = decodeURI("%E0%A4%A");
} catch (e) {
  console.error(e);
}

// URIError: malformed URI sequence
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-decodeuri-encodeduri]](https://tc39.es/ecma262/multipage/global-object.html#sec-decodeuri-encodeduri)

  -------------------------------------------------------------------------------------------------------------------


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

`decodeURI`

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

 
-   [`decodeURIComponent()`](decodeuricomponent)
-   [`encodeURI()`](encodeuri)
-   [`encodeURIComponent()`](encodeuricomponent)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/decodeURI>

