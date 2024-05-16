Intl.getCanonicalLocales()
==========================

 
The `Intl.getCanonicalLocales()` static method returns an array
containing the canonical locale names. Duplicates will be omitted and
elements will be validated as structurally valid language tags.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Intl.getCanonicalLocales(locales)
```




 
### Parameters

 

[`locales`](#locales)

:   A list of [`String`](../string) values for which to get the
    canonical locale names.



 
### Return value 

 
An array containing the canonical locale names.



 
Examples
--------


 
### Using getCanonicalLocales 

 
 
 
[js]


```js
Intl.getCanonicalLocales("EN-US"); // ["en-US"]
Intl.getCanonicalLocales(["EN-US", "Fr"]); // ["en-US", "fr"]

Intl.getCanonicalLocales("EN_US");
// RangeError:'EN_US' is not a structurally valid language tag
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.getcanonicallocales]](https://tc39.es/ecma402/#sec-intl.getcanonicallocales)

  -----------------------------------------------------------------------------------------------


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

`getCanonicalLocales`

54

16

48

41

10.1

54

56

41

10.3

6.0

54

1.8

7.0.0

 
See also 
--------

 
-   [Polyfill of `Intl.getCanonicalLocales` in
    FormatJS](https://formatjs.io/docs/polyfills/intl-getcanonicallocales/)
-   [`Intl.NumberFormat.supportedLocalesOf()`](numberformat/supportedlocalesof)
-   [`Intl.DateTimeFormat.supportedLocalesOf()`](datetimeformat/supportedlocalesof)
-   [`Intl.Collator.supportedLocalesOf()`](collator/supportedlocalesof)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/getCanonicalLocales>

