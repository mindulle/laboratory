Intl.ListFormat.supportedLocalesOf()
====================================

 
The `Intl.ListFormat.supportedLocalesOf()` static method returns an
array containing those of the provided locales that are supported in
list formatting without having to fall back to the runtime\'s default
locale.


 
Syntax
------

 
 
 
[js]


```js
Intl.ListFormat.supportedLocalesOf(locales)
Intl.ListFormat.supportedLocalesOf(locales, options)
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
are supported in list formatting without having to fall back to the
runtime\'s default locale.



 
Examples
--------


 
### Using supportedLocalesOf() 

 
Assuming a runtime that supports Indonesian and German but not Balinese
in list formatting, `supportedLocalesOf` returns the Indonesian and
German language tags unchanged, even though `pinyin` collation is
neither relevant to list formatting nor used with Indonesian, and a
specialized German for Indonesia is unlikely to be supported. Note the
specification of the `"lookup"` algorithm here --- a `"best fit"`
matcher might decide that Indonesian is an adequate match for Balinese
since most Balinese speakers also understand Indonesian, and therefore
return the Balinese language tag as well.

 
 
[js]


```js
const locales = ["ban", "id-u-co-pinyin", "de-ID"];
const options = { localeMatcher: "lookup" };
console.log(Intl.ListFormat.supportedLocalesOf(locales, options));
// ["id-u-co-pinyin", "de-ID"]
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.ListFormat.supportedLocalesOf]](https://tc39.es/ecma402/#sec-Intl.ListFormat.supportedLocalesOf)

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

`supportedLocalesOf`

72

79

78

60

14.1Only available on macOS Big Sur (11) and above.

72

79

51

14.5

11.0

72

1.8

13.0.0

12.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. To make full ICU (locale) data available before
version 13, see [Node.js documentation on the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

 
See also 
--------

 
-   [`Intl.ListFormat`](../listformat)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/supportedLocalesOf>

