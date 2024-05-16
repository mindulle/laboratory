Intl.Locale() constructor
=========================

 
The `Intl.Locale()` constructor creates [`Intl.Locale`](../locale)
objects.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Intl.Locale(tag)
new Intl.Locale(tag, options)
```


 
**Note:** `Intl.Locale()` can only be constructed with
[`new`](../../../operators/new). Attempting to call it without `new`
throws a [`TypeError`](../../typeerror).




 
### Parameters

 

[`tag`](#tag)

:   The Unicode locale identifier string. For the syntax of locale
    identifier strings, see the [Intl main
    page](../../intl#locales_argument). Note that the `Intl.Locale`
    constructor, unlike most other `Intl` constructors, does not accept
    an array of locales or `undefined`.

[`options`](#options)

:   An object that contains configuration for the Locale. Option values
    here take priority over extension keys in the locale identifier.
    Possible properties are:

    [`language`](#language)

    :   The language. Any syntactically valid string following the
        [`unicode_language_subtag`](https://unicode.org/reports/tr35/#unicode_language_subtag)
        grammar (2--3 or 5--8 letters) is accepted, but the
        implementation only recognizes certain kinds.

    [`script`](#script)

    :   The script. Any syntactically valid string following the
        [`unicode_script_subtag`](https://unicode.org/reports/tr35/#unicode_script_subtag)
        grammar (4 letters) is accepted, but the implementation only
        recognizes certain kinds.

    [`region`](#region)

    :   The region. Any syntactically valid string following the
        [`unicode_region_subtag`](https://unicode.org/reports/tr35/#unicode_region_subtag)
        grammar (either 2 letters or 3 digits) is accepted, but the
        implementation only recognizes certain kinds.

    [`calendar`](#calendar)

    :   The calendar. Any syntactically valid string following the
        [`type`](https://unicode.org/reports/tr35/#Unicode_locale_identifier)
        grammar (one or more segments of 3--8 alphanumerals, joined by
        hyphens) is accepted, but the implementation only recognizes
        certain kinds, which are listed in
        [`Intl.Locale.prototype.getCalendars`](getcalendars#supported_calendar_types).

    [`collation`](#collation)

    :   The collation. Any syntactically valid string following the
        `type` grammar is accepted, but the implementation only
        recognizes certain kinds, which are listed in
        [`Intl.Locale.prototype.getCollations`](getcollations#supported_collation_types).

    [`numberingSystem`](#numberingsystem)

    :   The numbering system. Any syntactically valid string following
        the `type` grammar is accepted, but the implementation only
        recognizes certain kinds, which are listed in
        [`Intl.Locale.prototype.getNumberingSystems`](getnumberingsystems#supported_numbering_systems).

    [`caseFirst`](#casefirst)

    :   The case-first sort option. Possible values are `"upper"`,
        `"lower"`, or `"false"`.

    [`hourCycle`](#hourcycle)

    :   The hour cycle. Possible values are `"h23"`, `"h12"`, `"h11"`,
        or the practically unused `"h24"`, which are explained in
        [`Intl.Locale.prototype.getHourCycles`](gethourcycles#supported_hour_cycle_types)

    [`numeric`](#numeric)

    :   The numeric sort option. A boolean.



 
Examples
--------


 
### Basic usage 

 
At its very simplest, the [`Intl.Locale()`](locale) constructor takes a
locale identifier string as its argument:

 
 
[js]


```js
const us = new Intl.Locale("en-US");
```




 
### Using the Locale constructor with an options object 

 
The constructor also takes an optional configuration object argument,
which can contain any of several extension types. For example, set the
[`hourCycle`](hourcycle) property of the configuration object to your
desired hour cycle type, and then pass it into the constructor:

 
 
[js]


```js
const locale = new Intl.Locale("en-US", { hourCycle: "h12" });
console.log(locale.hourCycle); // "h12"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl-locale-constructor]](https://tc39.es/ecma402/#sec-intl-locale-constructor)

  ---------------------------------------------------------------------------------------------


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

`Locale`

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

 
-   [Polyfill of `Intl.Locale` in
    FormatJS](https://formatjs.io/docs/polyfills/intl-locale/)
-   [`Intl.Collator`](../collator)
-   [Canonical Unicode Locale
    Identifiers](https://www.unicode.org/reports/tr35/#Canonical_Unicode_Locale_Identifiers)
    in the Unicode locale data markup language spec



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/Locale>

