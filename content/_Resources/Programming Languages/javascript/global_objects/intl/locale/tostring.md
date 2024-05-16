Intl.Locale.prototype.toString()
================================

 
The `toString()` method of [`Intl.Locale`](../locale) instances returns
this Locale\'s full [locale identifier
string](https://www.unicode.org/reports/tr35/#Unicode_locale_identifier).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toString()
```




 
### Parameters

 
None.



 
### Return value 

 
The *locale*\'s Unicode locale identifier string.



 
Description
-----------

 
The `Locale` object is a JavaScript representation of a concept Unicode
locale identifier. Information about a particular locale (language,
script, calendar type, etc.) can be encoded in a locale identifier
string. To make it easier to work with these locale identifiers, the
`Locale` object was introduced to JavaScript. Calling the `toString`
method on a Locale object will return the identifier string for that
particular Locale. The `toString` method allows `Locale` instances to be
provided as an argument to existing `Intl` constructors, serialized in
JSON, or any other context where an exact string representation is
useful.



 
Examples
--------


 
### Using toString 

 
 
 
[js]


```js
const myLocale = new Intl.Locale("fr-Latn-FR", {
  hourCycle: "h12",
  calendar: "gregory",
});
console.log(myLocale.baseName); // Prints "fr-Latn-FR"
console.log(myLocale.toString()); // Prints "fr-Latn-FR-u-ca-gregory-hc-h12"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.Locale.prototype.toString]](https://tc39.es/ecma402/#sec-Intl.Locale.prototype.toString)

  -----------------------------------------------------------------------------------------------------------


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

`toString`

74

79

75

62

14

74

79

53

14

11.0

74

1.8

12.0.0

 
See also 
--------

 
-   [`Intl.Locale`](../locale)
-   [`baseName`](basename)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/toString>

