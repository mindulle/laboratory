encodeURIComponent()
====================

 
The `encodeURIComponent()` function encodes a
[URI](https://developer.mozilla.org/en-US/docs/Glossary/URI) by
replacing each instance of certain characters by one, two, three, or
four escape sequences representing the
[UTF-8](https://developer.mozilla.org/en-US/docs/Glossary/UTF-8)
encoding of the character (will only be four escape sequences for
characters composed of two surrogate characters). Compared to
[`encodeURI()`](encodeuri), this function encodes more characters,
including those that are part of the URI syntax.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
encodeURIComponent(uriComponent)
```




 
### Parameters

 

[`uriComponent`](#uricomponent)

:   A string to be encoded as a URI component (a path, query string,
    fragment, etc.). Other values are [converted to
    strings](string#string_coercion).



 
### Return value 

 
A new string representing the provided `uriComponent` encoded as a URI
component.



 
### Exceptions

 

[`URIError`](urierror)

:   Thrown if `uriComponent` contains a [lone
    surrogate](string#utf-16_characters_unicode_code_points_and_grapheme_clusters).



 
Description
-----------

 
`encodeURIComponent()` is a function property of the global object.

`encodeURIComponent()` uses the same encoding algorithm as described in
[`encodeURI()`](encodeuri). It escapes all characters **except**:

```text
A–Z a–z 0–9 - _ . ! ~ * ' ( )
```

Compared to [`encodeURI()`](encodeuri), `encodeURIComponent()` escapes a
larger set of characters. Use `encodeURIComponent()` on user-entered
fields from forms
[`POST`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST)\'d
to the server --- this will encode `&` symbols that may inadvertently be
generated during data entry for special HTML entities or other
characters that require encoding/decoding. For example, if a user writes
`Jack & Jill`, without `encodeURIComponent()`, the ampersand could be
interpreted on the server as the start of a new field and jeopardize the
integrity of the data.

For
[`application/x-www-form-urlencoded`](https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#application/x-www-form-urlencoded-encoding-algorithm),
spaces are to be replaced by `+`, so one may wish to follow a
`encodeURIComponent()` replacement with an additional replacement of
`%20` with `+`.



 
Examples
--------


 
### Encoding for Content-Disposition and Link headers 

 
The following example provides the special encoding required within
UTF-8
[`Content-Disposition`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Disposition)
and
[`Link`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Link)
server response header parameters (e.g., UTF-8 filenames):

 
 
[js]


```js
const fileName = "my file(2).txt";
const header = `Content-Disposition: attachment; filename*=UTF-8''${encodeRFC5987ValueChars(
  fileName,
)}`;

console.log(header);
// "Content-Disposition: attachment; filename*=UTF-8''my%20file%282%29.txt"

function encodeRFC5987ValueChars(str) {
  return (
    encodeURIComponent(str)
      // The following creates the sequences %27 %28 %29 %2A (Note that
      // the valid encoding of "*" is %2A, which necessitates calling
      // toUpperCase() to properly encode). Although RFC3986 reserves "!",
      // RFC5987 does not, so we do not need to escape it.
      .replace(
        /['()*]/g,
        (c) => `%${c.charCodeAt(0).toString(16).toUpperCase()}`,
      )
      // The following are not required for percent-encoding per RFC5987,
      // so we can allow for a little better readability over the wire: |`^
      .replace(/%(7C|60|5E)/g, (str, hex) =>
        String.fromCharCode(parseInt(hex, 16)),
      )
  );
}
```




 
### Encoding for RFC3986 

 
The more recent [RFC3986](https://datatracker.ietf.org/doc/html/rfc3986)
reserves !, \', (, ), and \*, even though these characters have no
formalized URI delimiting uses. The following function encodes a string
for RFC3986-compliant URL component format. It also encodes \[ and \],
which are part of the
[IPv6](https://developer.mozilla.org/en-US/docs/Glossary/IPv6) URI
syntax. An RFC3986-compliant `encodeURI` implementation should not
escape them, which is demonstrated in the [`encodeURI()`
example](encodeuri#encoding_for_rfc3986).

 
 
[js]


```js
function encodeRFC3986URIComponent(str) {
  return encodeURIComponent(str).replace(
    /[!'()*]/g,
    (c) => `%${c.charCodeAt(0).toString(16).toUpperCase()}`,
  );
}
```




 
### Encoding a lone surrogate throws 

 
A [`URIError`](urierror) will be thrown if one attempts to encode a
surrogate which is not part of a high-low pair. For example:

 
 
[js]


```js
// High-low pair OK
encodeURIComponent("\uD800\uDFFF"); // "%F0%90%8F%BF"

// Lone high-surrogate code unit throws "URIError: malformed URI sequence"
encodeURIComponent("\uD800");

// Lone high-surrogate code unit throws "URIError: malformed URI sequence"
encodeURIComponent("\uDFFF");
```


You can use [`String.prototype.toWellFormed()`](string/towellformed),
which replaces lone surrogates with the Unicode replacement character
(U+FFFD), to avoid this error. You can also use
[`String.prototype.isWellFormed()`](string/iswellformed) to check if a
string contains lone surrogates before passing it to
`encodeURIComponent()`.



Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-encodeuricomponent-uricomponent]](https://tc39.es/ecma262/multipage/global-object.html#sec-encodeuricomponent-uricomponent)

  -----------------------------------------------------------------------------------------------------------------------------------------


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

`encodeURIComponent`

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
-   [`encodeURI()`](encodeuri)
-   [`decodeURIComponent()`](decodeuricomponent)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent>

