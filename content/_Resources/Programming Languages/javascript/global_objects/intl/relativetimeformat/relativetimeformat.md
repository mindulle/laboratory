Intl.RelativeTimeFormat() constructor
=====================================

 
The `Intl.RelativeTimeFormat()` constructor creates
[`Intl.RelativeTimeFormat`](../relativetimeformat) objects.


 
Syntax
------

 
 
 
[js]


```js
new Intl.RelativeTimeFormat()
new Intl.RelativeTimeFormat(locales)
new Intl.RelativeTimeFormat(locales, options)
```


 
**Note:** `Intl.RelativeTimeFormat()` can only be constructed with
[`new`](../../../operators/new). Attempting to call it without `new`
throws a [`TypeError`](../../typeerror).




 
### Parameters

 

[`locales`](#locales) [Optional]

:   A string with a BCP 47 language tag or an [`Intl.Locale`](../locale)
    instance, or an array of such locale identifiers. For the general
    form and interpretation of the `locales` argument, see [the
    parameter description on the `Intl` main
    page](../../intl#locales_argument).

    The following Unicode extension key is allowed:

    [`nu`](#nu)

    :   See [`numberingSystem`](#numberingsystem).

    This key can also be set with `options` (as listed below). When both
    are set, the `options` property takes precedence.

[`options`](#options) [Optional]

:   An object containing the following properties, in the order they are
    retrieved (all of them are optional):

    [`localeMatcher`](#localematcher)

    :   The locale matching algorithm to use. Possible values are
        `"lookup"` and `"best fit"`; the default is `"best fit"`. For
        information about this option, see [Locale identification and
        negotiation](../../intl#locale_identification_and_negotiation).

    [`numberingSystem`](#numberingsystem)

    :   The numbering system to use for number formatting, such as
        `"arab"`, `"hans"`, `"mathsans"`, and so on. For a list of
        supported numbering system types, see
        [`Intl.Locale.prototype.getNumberingSystems()`](../locale/getnumberingsystems#supported_numbering_system_types).
        This option can also be set through the `nu` Unicode extension
        key; if both are provided, this `options` property takes
        precedence.

    [`style`](#style)

    :   The style of the formatted relative time. Possible values are:

        [`"long"`](#long) (default)

        :   E.g., \"in 1 month\"

        [`"short"`](#short)

        :   E.g., \"in 1 mo.\"

        [`"narrow"`](#narrow)

        :   E.g., \"in 1 mo.\". The narrow style could be similar to the
            short style for some locales.

    [`numeric`](#numeric)

    :   Whether to use numeric values in the output. Possible values are
        `"always"` and `"auto"`; the default is `"always"`. When set to
        `"auto"`, the output may use more idiomatic phrasing such as
        `"yesterday"` instead of `"1 day ago"`.



 
### Exceptions

 

[`RangeError`](../../rangeerror)

:   Thrown if `locales` or `options` contain invalid values.



 
Examples
--------


 
### Basic format usage 

 
The following example shows how to create a relative time formatter
using the English language.

 
 
[js]


```js
// Create a relative time formatter in your locale
// with default values explicitly passed in.
const rtf = new Intl.RelativeTimeFormat("en", {
  localeMatcher: "best fit", // other values: "lookup"
  numeric: "always", // other values: "auto"
  style: "long", // other values: "short" or "narrow"
});

// Format relative time using negative value (-1).
rtf.format(-1, "day"); // "1 day ago"

// Format relative time using positive value (1).
rtf.format(1, "day"); // "in 1 day"
```




 
### Using the auto option 

 
If `numeric:auto` option is passed, it will produce the string
`yesterday` or `tomorrow` instead of `1 day ago` or `in 1 day`. This
allows to not always have to use numeric values in the output.

 
 
[js]


```js
// Create a relative time formatter in your locale
// with numeric: "auto" option value passed in.
const rtf = new Intl.RelativeTimeFormat("en", { numeric: "auto" });

// Format relative time using negative value (-1).
rtf.format(-1, "day"); // "yesterday"

// Format relative time using positive day unit (1).
rtf.format(1, "day"); // "tomorrow"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl-relativetimeformat-constructor]](https://tc39.es/ecma402/#sec-intl-relativetimeformat-constructor)

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

`RelativeTimeFormat`

71

79

65

58

14

71

65

50

14

10.0

71

1.8

13.0.0

12.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. When other locales are specified, the
`RelativeTimeFormat` instance silently falls back to `en-US`. To make
full ICU (locale) data available before version 13, see [Node.js
documentation on the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

 
See also 
--------

 
-   [`Intl.RelativeTimeFormat`](../relativetimeformat)
-   [`Intl`](../../intl)
-   [`Intl.RelativeTimeFormat`](https://v8.dev/features/intl-relativetimeformat)
    on v8.dev (2018)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/RelativeTimeFormat/RelativeTimeFormat>

