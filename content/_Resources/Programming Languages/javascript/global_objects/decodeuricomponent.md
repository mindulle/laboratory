decodeURIComponent()
====================

 
The `decodeURIComponent()` function decodes a Uniform Resource
Identifier (URI) component previously created by
[`encodeURIComponent()`](encodeuricomponent) or by a similar routine.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
decodeURIComponent(encodedURI)
```




 
### Parameters

 

[`encodedURI`](#encodeduri)

:   An encoded component of a Uniform Resource Identifier.



 
### Return value 

 
A new string representing the decoded version of the given encoded
Uniform Resource Identifier (URI) component.



 
### Exceptions

 

[`URIError`](urierror)

:   Thrown if `encodedURI` contains a `%` not followed by two
    hexadecimal digits, or if the escape sequence does not encode a
    valid UTF-8 character.



 
Description
-----------

 
`decodeURIComponent()` is a function property of the global object.

`decodeURIComponent()` uses the same decoding algorithm as described in
[`decodeURI()`](decodeuri). It decodes *all* escape sequences, including
those that are not created by
[`encodeURIComponent`](encodeuricomponent), like `-.!~*'()`.



 
Examples
--------


 
### Decoding a Cyrillic URL component 

 
 
 
[js]


```js
decodeURIComponent("JavaScript_%D1%88%D0%B5%D0%BB%D0%BB%D1%8B");
// "JavaScript_шеллы"
```




 
### Catching errors 

 
 
 
[js]


```js
try {
  const a = decodeURIComponent("%E0%A4%A");
} catch (e) {
  console.error(e);
}

// URIError: malformed URI sequence
```




 
### Decoding query parameters from a URL 

 
`decodeURIComponent()` cannot be used directly to parse query parameters
from a URL. It needs a bit of preparation.

 
 
[js]


```js
function decodeQueryParam(p) {
  return decodeURIComponent(p.replace(/\+/g, " "));
}

decodeQueryParam("search+query%20%28correct%29");
// 'search query (correct)'
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-decodeuricomponent-encodeduricomponent]](https://tc39.es/ecma262/multipage/global-object.html#sec-decodeuricomponent-encodeduricomponent)

  -------------------------------------------------------------------------------------------------------------------------------------------------------


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

`decodeURIComponent`

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

 
-   [`decodeURI`](decodeuri)
-   [`encodeURI`](encodeuri)
-   [`encodeURIComponent`](encodeuricomponent)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/decodeURIComponent>

