BigInt.prototype.toLocaleString()
=================================

Baseline [Widely available]
--------------------------------------


This feature is well established and works across many devices and
browser versions. It's been available across browsers since September
2020.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FBigInt%2FtoLocaleString&level=high)



The `toLocaleString()` method of [`BigInt`](../bigint) values returns a
string with a language-sensitive representation of this BigInt. In
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


A string representing the given BigInt according to language-specific
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
const bigint = 3500n;

console.log(bigint.toLocaleString());
// "3,500" if in U.S. English locale
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
const bigint = 123456789123456789n;

// German uses period for thousands
console.log(bigint.toLocaleString("de-DE"));
// 123.456.789.123.456.789

// Arabic in most Arabic speaking countries uses Eastern Arabic digits
console.log(bigint.toLocaleString("ar-EG"));
// ١٢٣٬٤٥٦٬٧٨٩٬١٢٣٬٤٥٦٬٧٨٩

// India uses thousands/lakh/crore separators
console.log(bigint.toLocaleString("en-IN"));
// 1,23,45,67,89,12,34,56,789

// the nu extension key requests a numbering system, e.g. Chinese decimal
console.log(bigint.toLocaleString("zh-Hans-CN-u-nu-hanidec"));
// 一二三,四五六,七八九,一二三,四五六,七八九

// when requesting a language that may not be supported, such as
// Balinese, include a fallback language, in this case Indonesian
console.log(bigint.toLocaleString(["ban", "id"]));
// 123.456.789.123.456.789
```





### Using options 


The results provided by `toLocaleString()` can be customized using the
`options` parameter:



[js]


```js
const bigint = 123456789123456789n;

// request a currency format
console.log(
  bigint.toLocaleString("de-DE", { style: "currency", currency: "EUR" }),
);
// 123.456.789.123.456.789,00 €

// the Japanese yen doesn't use a minor unit
console.log(
  bigint.toLocaleString("ja-JP", { style: "currency", currency: "JPY" }),
);
// ￥123,456,789,123,456,789

// limit to three significant digits
console.log(bigint.toLocaleString("en-IN", { maximumSignificantDigits: 3 }));
// 1,23,00,00,00,00,00,00,000
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sup-bigint.prototype.tolocalestring]](https://tc39.es/ecma402/#sup-bigint.prototype.tolocalestring)

  -------------------------------------------------------------------------------------------------------------


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

67

79

68

54

14

67

68

48

14

9.0

67

1.0

10.4.0

`locales`

76

79

70

No

14

76

79

54

14

12.0

76

1.8

1.0--1.8Only the locale data for `en-US` is available.

12.9.0

`options`

76

79

70

No

14

76

79

54

14

12.0

76

?

12.9.0


See also 
--------


-   [`Intl.NumberFormat`](../intl/numberformat)
-   [`BigInt.prototype.toString()`](tostring)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt/toLocaleString>

