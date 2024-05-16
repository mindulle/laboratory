Intl.PluralRules.supportedLocalesOf()
=====================================

 
The `Intl.PluralRules.supportedLocalesOf()` static method returns an
array containing those of the provided locales that are supported in
plural rules without having to fall back to the runtime\'s default
locale.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Intl.PluralRules.supportedLocalesOf(locales)
Intl.PluralRules.supportedLocalesOf(locales, options)
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
are supported in plural rules without having to fall back to the
runtime\'s default locale.



 
Examples
--------


 
### Using supportedLocalesOf() 

 
Assuming a runtime that supports Indonesian and German but not Balinese
in plural rules, `supportedLocalesOf` returns the Indonesian and German
language tags unchanged, even though `pinyin` collation is neither
relevant to plural rules nor used with Indonesian, and a specialized
German for Indonesia is unlikely to be supported. Note the specification
of the `"lookup"` algorithm here --- a `"best fit"` matcher might decide
that Indonesian is an adequate match for Balinese since most Balinese
speakers also understand Indonesian, and therefore return the Balinese
language tag as well.

 
 
[js]


```js
const locales = ["ban", "id-u-co-pinyin", "de-ID"];
const options = { localeMatcher: "lookup" };
console.log(Intl.PluralRules.supportedLocalesOf(locales, options));
// ["id-u-co-pinyin", "de-ID"]
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.pluralrules.supportedlocalesof]](https://tc39.es/ecma402/#sec-intl.pluralrules.supportedlocalesof)

  ---------------------------------------------------------------------------------------------------------------------


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

63

18

58

50

13

63

58

46

13

8.0

63

1.8

10.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `PluralRules()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/PluralRules/PluralRules)
for more details.

 
See also 
--------

 
-   [`Intl.PluralRules`](../pluralrules)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/PluralRules/supportedLocalesOf>

