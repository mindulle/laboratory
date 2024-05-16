Intl.DurationFormat.supportedLocalesOf()
========================================

 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `Intl.DurationFormat.supportedLocalesOf()` static method returns an
array containing those of the provided locales that are supported in
duration formatting without having to fall back to the runtime\'s
default locale.


 
Syntax
------

 
 
 
[js]


```js
Intl.DurationFormat.supportedLocalesOf(locales)
Intl.DurationFormat.supportedLocalesOf(locales, options)
```




 
### Parameters

 

[`locales`](#locales)

:   A string with a BCP 47 language tag, or an array of such strings.
    For the general form and interpretation of the `locales` argument,
    see [the parameter description on the `Intl` main
    page](../../intl#locales_argument).

[`options`](#options) [Optional]

:   An object that may have the following property:

    [`localeMatcher`](#localematcher)

    :   The locale matching algorithm to use. Possible values are
        `"lookup"` and `"best fit"`; the default is `"best fit"`. For
        information about this option, see the
        [Intl](../../intl#locale_identification_and_negotiation) page.



 
### Return value 

 
An array of strings representing a subset of the given locale tags that
are supported in duration formatting without having to fall back to the
runtime\'s default locale.



 
Examples
--------


 
### Using supportedLocalesOf() 

 
Assuming a runtime that supports Indonesian and German but not Balinese
in duration formatting, `supportedLocalesOf` returns the Indonesian and
German language tags unchanged, even though `pinyin` collation is
neither relevant to duration formatting nor used with Indonesian, and a
specialized German for Indonesia is unlikely to be supported. Note the
specification of the `"lookup"` algorithm here --- a `"best fit"`
matcher might decide that Indonesian is an adequate match for Balinese
since most Balinese speakers also understand Indonesian, and therefore
return the Balinese language tag as well.

 
 
[js]


```js
const locales = ["ban", "id-u-co-pinyin", "de-ID"];
const options = { localeMatcher: "lookup" };
console.log(Intl.DurationFormat.supportedLocalesOf(locales, options));
// ["id-u-co-pinyin", "de-ID"]
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------
  [Intl.DurationFormat\
  [\#
  sec-Intl.DurationFormat.supportedLocalesOf]](https://tc39.es/proposal-intl-duration-format/#sec-Intl.DurationFormat.supportedLocalesOf)

  -------------------------------------------------------------------------------------------------------------------------------------------------


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

`supportedLocalesOf`

No

No

No

No

16.4

No

No

No

16.4

No

No

No

No

 
See also 
--------

 
-   [`Intl.DurationFormat`](../durationformat)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DurationFormat/supportedLocalesOf>

