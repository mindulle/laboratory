Number.prototype.toLocaleString()
=================================

 
The `toLocaleString()` method of [`Number`](../number) values returns a
string with a language-sensitive representation of this number. In
implementations with [`Intl.NumberFormat` API](../intl/numberformat)
support, this method simply calls `Intl.NumberFormat`.

Every time `toLocaleString` is called, it has to perform a search in a
big database of localization strings, which is potentially inefficient.
When the method is called many times with the same arguments, it is
better to create a [`Intl.NumberFormat`](../intl/numberformat) object
and use its [`format()`](../intl/numberformat/format) method, because a
`NumberFormat` object remembers the arguments passed to it and may
decide to cache a slice of the database, so future `format` calls can
search for localization strings within a more constrained context.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toLocaleString()
toLocaleString(locales)
toLocaleString(locales, options)
```




 
### Parameters

 
The `locales` and `options` parameters customize the behavior of the
function and let applications specify the language whose formatting
conventions should be used.

In implementations that support the [`Intl.NumberFormat`
API](../intl/numberformat), these parameters correspond exactly to the
[`Intl.NumberFormat()`](../intl/numberformat/numberformat)
constructor\'s parameters. Implementations without `Intl.NumberFormat`
support are asked to ignore both parameters, making the locale used and
the form of the string returned entirely implementation-dependent.

[`locales`](#locales) [Optional]

:   A string with a BCP 47 language tag, or an array of such strings.
    Corresponds to the
    [`locales`](../intl/numberformat/numberformat#locales) parameter of
    the `Intl.NumberFormat()` constructor.

    In implementations without `Intl.NumberFormat` support, this
    parameter is ignored and the host\'s locale is usually used.

[`options`](#options) [Optional]

:   An object adjusting the output format. Corresponds to the
    [`options`](../intl/numberformat/numberformat#options) parameter of
    the `Intl.NumberFormat()` constructor.

    In implementations without `Intl.NumberFormat` support, this
    parameter is ignored.

See the [`Intl.NumberFormat()`
constructor](../intl/numberformat/numberformat) for details on these
parameters and how to use them.



 
### Return value 

 
A string representing the given number according to language-specific
conventions.

In implementations with `Intl.NumberFormat`, this is equivalent to
`new Intl.NumberFormat(locales, options).format(number)`.

 
**Note:** Most of the time, the formatting returned by
`toLocaleString()` is consistent. However, the output may vary with
time, language, and implementation --- output variations are by design
and allowed by the specification. You should not compare the results of
`toLocaleString()` to static values.




 
Examples
--------


 
### Using toLocaleString() 

 
Basic use of this method without specifying a `locale` returns a
formatted string in the default locale and with default options.

 
 
[js]


```js
const number = 3500;

console.log(number.toLocaleString()); // "3,500" if in U.S. English locale
```




 
### Checking for support for locales and options parameters 

 
The `locales` and `options` parameters may not be supported in all
implementations, because support for the internationalization API is
optional, and some systems may not have the necessary data. For
implementations without internationalization support, `toLocaleString()`
always uses the system\'s locale, which may not be what you want.
Because any implementation that supports the `locales` and `options`
parameters must support the [`Intl`](../intl) API, you can check the
existence of the latter for support:

 
 
[js]


```js
function toLocaleStringSupportsLocales() {
  return (
    typeof Intl === "object" &&
    !!Intl &&
    typeof Intl.NumberFormat === "function"
  );
}
```




 
### Using locales 

 
This example shows some of the variations in localized number formats.
In order to get the format of the language used in the user interface of
your application, make sure to specify that language (and possibly some
fallback languages) using the `locales` argument:

 
 
[js]


```js
const number = 123456.789;

// German uses comma as decimal separator and period for thousands
console.log(number.toLocaleString("de-DE"));
// 123.456,789

// Arabic in most Arabic speaking countries uses Eastern Arabic digits
console.log(number.toLocaleString("ar-EG"));
// ١٢٣٤٥٦٫٧٨٩

// India uses thousands/lakh/crore separators
console.log(number.toLocaleString("en-IN"));
// 1,23,456.789

// the nu extension key requests a numbering system, e.g. Chinese decimal
console.log(number.toLocaleString("zh-Hans-CN-u-nu-hanidec"));
// 一二三,四五六.七八九

// when requesting a language that may not be supported, such as
// Balinese, include a fallback language, in this case Indonesian
console.log(number.toLocaleString(["ban", "id"]));
// 123.456,789
```




 
### Using options 

 
The results provided by `toLocaleString()` can be customized using the
`options` parameter:

 
 
[js]


```js
const number = 123456.789;

// request a currency format
console.log(
  number.toLocaleString("de-DE", { style: "currency", currency: "EUR" }),
);
// 123.456,79 €

// the Japanese yen doesn't use a minor unit
console.log(
  number.toLocaleString("ja-JP", { style: "currency", currency: "JPY" }),
);
// ￥123,457

// limit to three significant digits
console.log(number.toLocaleString("en-IN", { maximumSignificantDigits: 3 }));
// 1,23,000

// Use the host default language with options for number formatting
const num = 30000.65;
console.log(
  num.toLocaleString(undefined, {
    minimumFractionDigits: 2,
    maximumFractionDigits: 2,
  }),
);
// "30,000.65" where English is the default language, or
// "30.000,65" where German is the default language, or
// "30 000,65" where French is the default language
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.prototype.tolocalestring]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.prototype.tolocalestring)

  [ECMAScript Internationalization API Specification\
  [\# sup-number.prototype.tolocalestring]](https://tc39.es/ecma402/#sup-number.prototype.tolocalestring)
  ---------------------------------------------------------------------------------------------------------------------------------------------


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

`toLocaleString`

1

12Before Edge 18, numbers are rounded to 15 decimal digits. For example,
`(1000000000000005).toLocaleString('en-US')` returns
`"1,000,000,000,000,010"`.

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`locales`

24

12

29

15

10

26

56

14

10

1.5

4.4

1.8

1.0--1.8Only the locale data for `en-US` is available.

13.0.0

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. When other locales are specified, the function
silently falls back to `en-US`. To make full ICU (locale) data available
before version 13, see [Node.js documentation on the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

`options`

24

12

29

15

10

26

56

14

10

1.5

4.4

1.0

0.12.0

 
See also 
--------

 
-   [`Intl.NumberFormat`](../intl/numberformat)
-   [`Number.prototype.toString()`](tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toLocaleString>

