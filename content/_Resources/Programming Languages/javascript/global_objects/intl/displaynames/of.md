Intl.DisplayNames.prototype.of()
================================

 
The `of()` method of [`Intl.DisplayNames`](../displaynames) instances
receives a code and returns a string based on the locale and options
provided when instantiating this `Intl.DisplayNames` object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
of(code)
```




 
### Parameters

 

[`code`](#code)

:   The `code` to provide depends on the `type`:

    -   If the type is \"region\", `code` should be either an
        [two-letter ISO 3166 region
        code](https://www.iso.org/iso-3166-country-codes.html), or a
        [three-digit UN M49 geographic
        region](https://unstats.un.org/unsd/methodology/m49/). It is
        required to follow the
        [`unicode_region_subtag`](https://unicode.org/reports/tr35/#unicode_region_subtag)
        grammar.
    -   If the type is \"script\", `code` should be an [four-letter ISO
        15924 script
        code](https://unicode.org/iso15924/iso15924-codes.html). It is
        required to follow the
        [`unicode_script_subtag`](https://unicode.org/reports/tr35/#unicode_script_subtag)
        grammar.
    -   If the type is \"language\", `code` should be a *languageCode*
        \[\"-\" *scriptCode*\] \[\"-\" *regionCode* \] \*(\"-\"
        *variant* ) subsequence of the
        [`unicode_language_id`](https://unicode.org/reports/tr35/#Unicode_language_identifier)
        grammar. *languageCode* is either a two-letter ISO 639-1
        language code or a three-letter ISO 639-2 language code.
    -   If the type is \"currency\", `code` should be a [three-letter
        ISO 4217 currency
        code](https://www.iso.org/iso-4217-currency-codes.html). It is
        required to have exactly three alphabetic characters.
    -   If the type is \"dateTimeField\", `code` should be one of:
        `"era"`, `"year"`, `"quarter"`, `"month"`, `"weekOfYear"`,
        `"weekday"`, `"day"`, `"dayPeriod"`, `"hour"`, `"minute"`,
        `"second"`, `"timeZoneName"`.
    -   If the type is \"calendar\", `code` should be a [calendar
        key](../locale/calendar). It is required to follow the `type`
        grammar of a [Unicode locale
        identifier](https://unicode.org/reports/tr35/#32-unicode-locale-identifier).



 
### Return value 

 
A language-specific formatted string, or `undefined` if there\'s no data
for the input and `fallback` is `"none"`.

 
**Note:** `fallback` is only used if `code` is structurally valid. See
[using fallback](#using_fallback).




 
### Exceptions

 

[`RangeError`](../../rangeerror)

:   Thrown if `code` is not structurally valid for the given `type`.



 
Examples
--------


 
### Using the of method 

 
 
 
[js]


```js
const regionNames = new Intl.DisplayNames("en", { type: "region" });
regionNames.of("419"); // "Latin America"

const languageNames = new Intl.DisplayNames("en", { type: "language" });
languageNames.of("fr"); // "French"

const currencyNames = new Intl.DisplayNames("en", { type: "currency" });
currencyNames.of("EUR"); // "Euro"
```




 
### Using fallback 

 
When the `Intl.DisplayNames` is constructed with `fallback: "code"`, the
`of()` method will return the `code` if the input looks structurally
valid but there\'s no data for the input. If `fallback` is `"none"`,
`undefined` is returned.

 
 
[js]


```js
console.log(
  new Intl.DisplayNames("en", { type: "region", fallback: "code" }).of("ZL"),
); // "ZL"

console.log(
  new Intl.DisplayNames("en", { type: "region", fallback: "none" }).of("ZL"),
); // undefined
```


However, this only applies if the `code` is structurally valid. For
example, if `type` is `"region"` but `code` does not follow the
`unicode_region_subtag` grammar (2 alphabetic characters or 3 numeric
characters), a [`RangeError`](../../rangeerror) is directly thrown
instead of using the fallback.

 
 
[js]


```js
console.log(
  new Intl.DisplayNames("en", { type: "region", fallback: "code" }).of("ZLC"),
); // throws RangeError: invalid value "ZLC" for option region
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.DisplayNames.prototype.of]](https://tc39.es/ecma402/#sec-Intl.DisplayNames.prototype.of)

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

`of`

81

81

86

68

14.1

81

86

58

14.5

13.0

81

1.8

14.0.0

 
See also 
--------

 
-   [`Intl.DisplayNames`](../displaynames)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DisplayNames/of>

