Intl.DisplayNames() constructor
===============================

 
The `Intl.DisplayNames()` constructor creates
[`Intl.DisplayNames`](../displaynames) objects.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Intl.DisplayNames(locales, options)
```


 
**Note:** `Intl.DisplayNames()` can only be constructed with
[`new`](../../../operators/new). Attempting to call it without `new`
throws a [`TypeError`](../../typeerror).




 
### Parameters

 

[`locales`](#locales)

:   A string with a BCP 47 language tag or an [`Intl.Locale`](../locale)
    instance, or an array of such locale identifiers. For the general
    form and interpretation of the `locales` argument, see [the
    parameter description on the `Intl` main
    page](../../intl#locales_argument).

[`options`](#options)

:   An object containing the following properties, in the order they are
    retrieved:

    [`localeMatcher`](#localematcher) [Optional]

    :   The locale matching algorithm to use. Possible values are
        `"lookup"` and `"best fit"`; the default is `"best fit"`. For
        information about this option, see [Locale identification and
        negotiation](../../intl#locale_identification_and_negotiation).

    [`style`](#style) [Optional]

    :   The formatting style to use. Possible values are `"narrow"`,
        `"short"`, and `"long"`; the default is `"long"`.

    [`type`](#type)

    :   The type of display names to return from [`of()`](of). Possible
        values are `"language"`, `"region"`, `"script"`, `"currency"`,
        `"calendar"`, and `"dateTimeField"`.

    [`fallback`](#fallback) [Optional]

    :   What to return from `of()` if the input is structurally valid
        but there\'s no matching display name. Possible values are:

        [`"code"`](#code) (default)

        :   Return the input code itself.

        [`"none"`](#none)

        :   Return `undefined`.

    [`languageDisplay`](#languagedisplay) [Optional]

    :   How language names should be displayed. Only usable along with
        `type: "language"`. Possible values are:

        [`"dialect"`](#dialect) (default)

        :   Display special regional dialects using their own name. E.g.
            `"nl-BE"` will be displayed as `"Flemish"`.

        [`"standard"`](#standard)

        :   Display all languages using standard format. E.g. `"nl-BE"`
            will be displayed as `"Dutch (Belgium)"`.



 
### Exceptions

 

[`TypeError`](../../typeerror)

:   Thrown if `options.type` is not provided.

[`RangeError`](../../rangeerror)

:   Thrown if `locales` or `options` contain invalid values.



 
Examples
--------


 
### Basic usage 

 
In basic use without specifying a locale, a formatted string in the
default locale and with default options is returned.

 
 
[js]


```js
console.log(new Intl.DisplayNames([], { type: "language" }).of("US"));
// 'us'
```




 
### Using type `dateTimeField` 

 
Example using `dateTimeField` as a type option, will return the
localized date time names strings.

 
 
[js]


```js
const dn = new Intl.DisplayNames("pt", { type: "dateTimeField" });
console.log(dn.of("era")); // 'era'
console.log(dn.of("year")); // 'ano'
console.log(dn.of("month")); // 'mês'
console.log(dn.of("quarter")); // 'trimestre'
console.log(dn.of("weekOfYear")); // 'semana'
console.log(dn.of("weekday")); // 'dia da semana'
console.log(dn.of("dayPeriod")); // 'AM/PM'
console.log(dn.of("day")); // 'dia'
console.log(dn.of("hour")); // 'hora'
console.log(dn.of("minute")); // 'minuto'
console.log(dn.of("second")); // 'segundo'
```




 
### Using type `calendar` 

 
Example using `calendar` as a type option, will return the localized
calendar names strings.

 
 
[js]


```js
const dn = new Intl.DisplayNames("en", { type: "calendar" });
console.log(dn.of("roc")); // 'Minguo Calendar'
console.log(dn.of("gregory")); // 'Gregorian Calendar'
console.log(dn.of("chinese")); // 'Chinese Calendar'
```




 
### Using type `language` with `languageDisplay` 

 
Example using `language` as a type with `languageDisplay` options.

 
 
[js]


```js
// Using `dialect` option
const dnDialect = new Intl.DisplayNames("en", {
  type: "language",
  languageDisplay: "dialect",
});
console.log(dnDialect.of("en-GB")); // 'British English'

// Using `standard` option
const dnStd = new Intl.DisplayNames("en", {
  type: "language",
  languageDisplay: "standard",
});
console.log(dnStd.of("en-GB")); // 'English (United Kingdom)'
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl-displaynames-constructor]](https://tc39.es/ecma402/#sec-intl-displaynames-constructor)

  ---------------------------------------------------------------------------------------------------------


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

`DisplayNames`

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
-   [`Intl.supportedValuesOf()`](../supportedvaluesof)
-   [`Intl`](../../intl)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DisplayNames/DisplayNames>

