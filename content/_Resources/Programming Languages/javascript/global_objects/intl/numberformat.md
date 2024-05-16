Intl.NumberFormat
=================

 
The `Intl.NumberFormat` object enables language-sensitive number
formatting.


 
Try it 
------

 



 
Constructor
-----------

 

[`Intl.NumberFormat()`](numberformat/numberformat)

:   Creates a new `NumberFormat` object.



 
Static methods 
--------------

 

[`Intl.NumberFormat.supportedLocalesOf()`](numberformat/supportedlocalesof)

:   Returns an array containing those of the provided locales that are
    supported without having to fall back to the runtime\'s default
    locale.



 
Instance properties 
-------------------

 
These properties are defined on `Intl.NumberFormat.prototype` and shared
by all `Intl.NumberFormat` instances.

[`Intl.NumberFormat.prototype.constructor`](../object/constructor)

:   The constructor function that created the instance object. For
    `Intl.NumberFormat` instances, the initial value is the
    [`Intl.NumberFormat`](numberformat/numberformat) constructor.

[`Intl.NumberFormat.prototype[@@toStringTag]`](#intl.numberformat.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](../symbol/tostringtag)
    property is the string `"Intl.NumberFormat"`. This property is used
    in [`Object.prototype.toString()`](../object/tostring).



 
Instance methods 
----------------

 

[`Intl.NumberFormat.prototype.format()`](numberformat/format)

:   Getter function that formats a number according to the locale and
    formatting options of this [`Intl.NumberFormat`](numberformat)
    object.

[`Intl.NumberFormat.prototype.formatRange()`](numberformat/formatrange)

:   Getter function that formats a range of numbers according to the
    locale and formatting options of the
    [`Intl.NumberFormat`](numberformat) object from which the method is
    called.

[`Intl.NumberFormat.prototype.formatRangeToParts()`](numberformat/formatrangetoparts)

:   Returns an [`Array`](../array) of objects representing the range of
    number strings in parts that can be used for custom locale-aware
    formatting.

[`Intl.NumberFormat.prototype.formatToParts()`](numberformat/formattoparts)

:   Returns an [`Array`](../array) of objects representing the number
    string in parts that can be used for custom locale-aware formatting.

[`Intl.NumberFormat.prototype.resolvedOptions()`](numberformat/resolvedoptions)

:   Returns a new object with properties reflecting the locale and
    collation options computed during initialization of the object.



 
Examples
--------


 
### Basic usage 

 
In basic use without specifying a locale, a formatted string in the
default locale and with default options is returned.

 
 
[js]


```js
const number = 3500;

console.log(new Intl.NumberFormat().format(number));
// '3,500' if in US English locale
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
console.log(new Intl.NumberFormat("de-DE").format(number));
// 123.456,789

// Arabic in most Arabic speaking countries uses real Arabic digits
console.log(new Intl.NumberFormat("ar-EG").format(number));
// ١٢٣٤٥٦٫٧٨٩

// India uses thousands/lakh/crore separators
console.log(new Intl.NumberFormat("en-IN").format(number));
// 1,23,456.789

// the nu extension key requests a numbering system, e.g. Chinese decimal
console.log(new Intl.NumberFormat("zh-Hans-CN-u-nu-hanidec").format(number));
// 一二三,四五六.七八九

// when requesting a language that may not be supported, such as
// Balinese, include a fallback language, in this case Indonesian
console.log(new Intl.NumberFormat(["ban", "id"]).format(number));
// 123.456,789
```




 
### Using options 

 
The results can be customized using the
[`options`](numberformat/numberformat#options) argument:

 
 
[js]


```js
const number = 123456.789;

// request a currency format
console.log(
  new Intl.NumberFormat("de-DE", { style: "currency", currency: "EUR" }).format(
    number,
  ),
);
// 123.456,79 €

// the Japanese yen doesn't use a minor unit
console.log(
  new Intl.NumberFormat("ja-JP", { style: "currency", currency: "JPY" }).format(
    number,
  ),
);
// ￥123,457

// limit to three significant digits
console.log(
  new Intl.NumberFormat("en-IN", { maximumSignificantDigits: 3 }).format(
    number,
  ),
);
// 1,23,000

// Formatting with units
console.log(
  new Intl.NumberFormat("pt-PT", {
    style: "unit",
    unit: "kilometer-per-hour",
  }).format(50),
);
// 50 km/h

console.log(
  (16).toLocaleString("en-GB", {
    style: "unit",
    unit: "liter",
    unitDisplay: "long",
  }),
);
// 16 litres
```


For an exhaustive list of options, see the [`Intl.NumberFormat()`
constructor](numberformat/numberformat#options) page.



Specifications
--------------

 
  -------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  numberformat-objects]](https://tc39.es/ecma402/#numberformat-objects)

  -------------------------------------------------------------------------------


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

`NumberFormat`

24

12

29

15

10

25

56

14

10

1.5

4.4

1.8

0.12.0

`NumberFormat`

24

12

29

15

10

25

56

14

10

1.5

4.4

1.8

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `NumberFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/NumberFormat)
for more details.

`format`

24

12Before Edge 18, numbers are rounded to 15 decimal digits. For example,
`new Intl.NumberFormat('en-US').format(1000000000000005)` returns
`"1,000,000,000,000,010"`.

29

15

10

25

56

14

10

1.5

4.4

1.8

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `NumberFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/NumberFormat)
for more details.

`formatRange`

106

106

116

92

15.4

106

116

72

15.4

20.0

106

No

19.0.0

`formatRangeToParts`

106

106

116

92

15.4

106

116

72

15.4

20.0

106

No

19.0.0

`formatToParts`

64

12

58

51

13

64

58

47

13

9.0

64

1.8

10.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `NumberFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/NumberFormat)
for more details.

`resolvedOptions`

24

12

29

15

10

25

56

14

10

1.5

4.4

1.8

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `NumberFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/NumberFormat)
for more details.

`supportedLocalesOf`

24

12

29

15

10

25

56

14

10

1.5

4.4

1.8

13.0.0

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. To make full ICU (locale) data available before
version 13, see [Node.js documentation on the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

 
See also 
--------

 
-   [Polyfill of `Intl.NumberFormat` in
    FormatJS](https://formatjs.io/docs/polyfills/intl-numberformat/)
-   [`Intl`](../intl)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat>

