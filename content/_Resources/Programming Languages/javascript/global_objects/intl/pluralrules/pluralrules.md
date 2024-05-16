Intl.PluralRules() constructor
==============================

 
The `Intl.PluralRules()` constructor creates
[`Intl.PluralRules`](../pluralrules) objects.


 
Syntax
------

 
 
 
[js]


```js
new Intl.PluralRules()
new Intl.PluralRules(locales)
new Intl.PluralRules(locales, options)
```


 
**Note:** `Intl.PluralRules()` can only be constructed with
[`new`](../../../operators/new). Attempting to call it without `new`
throws a [`TypeError`](../../typeerror).




 
### Parameters

 

[`locales`](#locales) [Optional]

:   A string with a BCP 47 language tag or an [`Intl.Locale`](../locale)
    instance, or an array of such locale identifiers. For the general
    form and interpretation of the `locales` argument, see [the
    parameter description on the `Intl` main
    page](../../intl#locales_argument).

[`options`](#options) [Optional]

:   An object containing the following properties, in the order they are
    retrieved (all of them are optional):

    [`localeMatcher`](#localematcher)

    :   The locale matching algorithm to use. Possible values are
        `"lookup"` and `"best fit"`; the default is `"best fit"`. For
        information about this option, see [Locale identification and
        negotiation](../../intl#locale_identification_and_negotiation).

    [`type`](#type)

    :   The type to use. Possible values are:

        [`"cardinal"`](#cardinal) (default)

        :   For cardinal numbers (referring to the quantity of things).

        [`"ordinal"`](#ordinal)

        :   For ordinal number (referring to the ordering or ranking of
            things, e.g. \"1st\", \"2nd\", \"3rd\" in English).

    `Intl.PluralRules` also supports the `Intl.NumberFormat()` [digit
    options](../numberformat/numberformat#digit_options) (see
    `Intl.NumberFormat()` for details):

    -   `minimumIntegerDigits`
    -   `minimumFractionDigits`
    -   `maximumFractionDigits`
    -   `minimumSignificantDigits`
    -   `maximumSignificantDigits`
    -   `roundingPriority`
    -   `roundingIncrement`
    -   `roundingMode`

    These options are interpreted as if the `notation` option from
    `Intl.NumberFormat` is `"standard"` and `style` is `"decimal"`.



 
### Exceptions

 

[`RangeError`](../../rangeerror)

:   Thrown if `locales` or `options` contain invalid values.



 
Examples
--------


 
### Basic usage 

 
In basic use without specifying a locale, a formatted string in the
default locale and with default options is returned. This is useful to
distinguish between singular and plural forms, e.g. \"dog\" and
\"dogs\".

 
 
[js]


```js
const pr = new Intl.PluralRules();

pr.select(0); // 'other' if in US English locale

pr.select(1); // 'one' if in US English locale

pr.select(2); // 'other' if in US English locale
```




 
### Using options 

 
The results can be customized using the `options` argument, which has
one property called `type` which you can set to `ordinal`. This is
useful to figure out the ordinal indicator, e.g. \"1st\", \"2nd\",
\"3rd\", \"4th\", \"42nd\", and so forth.

 
 
[js]


```js
const pr = new Intl.PluralRules("en-US", { type: "ordinal" });

const suffixes = new Map([
  ["one", "st"],
  ["two", "nd"],
  ["few", "rd"],
  ["other", "th"],
]);
const formatOrdinals = (n) => {
  const rule = pr.select(n);
  const suffix = suffixes.get(rule);
  return `${n}${suffix}`;
};

formatOrdinals(0); // '0th'
formatOrdinals(1); // '1st'
formatOrdinals(2); // '2nd'
formatOrdinals(3); // '3rd'
formatOrdinals(4); // '4th'
formatOrdinals(11); // '11th'
formatOrdinals(21); // '21st'
formatOrdinals(42); // '42nd'
formatOrdinals(103); // '103rd'
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl-pluralrules-constructor]](https://tc39.es/ecma402/#sec-intl-pluralrules-constructor)

  -------------------------------------------------------------------------------------------------------


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

`PluralRules`

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

13.0.0

10.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. When other locales are specified, the
`PluralRules` instance silently falls back to `en-US`. To make full ICU
(locale) data available before version 13, see [Node.js documentation on
the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

`options_roundingIncrement_parameter`

No

No

116

No

No

No

116

No

No

No

No

No

No

`options_roundingMode_parameter`

No

No

116

No

No

No

116

No

No

No

No

No

No

`options_roundingPriority_parameter`

No

No

116

No

No

No

116

No

No

No

No

No

No

`options_trailingZeroDisplay_parameter`

No

No

116

No

No

No

116

No

No

No

No

No

No

 
See also 
--------

 
-   [`Intl.PluralRules`](../pluralrules)
-   [`Intl`](../../intl)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/PluralRules/PluralRules>

