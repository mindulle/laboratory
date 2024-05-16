Intl.NumberFormat.prototype.formatRangeToParts()
================================================

 
The `formatRangeToParts()` method of
[`Intl.NumberFormat`](../numberformat) instances returns an
[`Array`](../../array) of objects containing the locale-specific tokens
from which it is possible to build custom strings while preserving the
locale-specific parts. This makes it possible to provide locale-aware
custom formatting ranges of number strings.


 
Syntax
------

 
 
 
[js]


```js
formatRangeToParts(startRange, endRange)
```




 
### Parameters

 

[`startRange`](#startrange)

:   A [`Number`](../../number) or [`BigInt`](../../bigint).

[`endRange`](#endrange)

:   A [`Number`](../../number) or [`BigInt`](../../bigint).



 
### Return value 

 
An [`Array`](../../array) of objects containing the formatted range of
numbers in parts.

The structure of the returned looks like this:

 
 
[js]


```js
[
  { type: "integer", value: "3", source: "startRange" },
  { type: "literal", value: "-", source: "shared" },
  { type: "integer", value: "5", source: "endRange" },
  { type: "literal", value: " ", source: "shared" },
  { type: "currency", value: "€", source: "shared" },
];
```


Possible values for the `type` property include:

[`currency`](#currency)

:   The currency string, such as the symbols \"\$\" and \"€\" or the
    name \"Dollar\", \"Euro\", depending on how `currencyDisplay` is
    specified.

[`decimal`](#decimal)

:   The decimal separator string (\".\").

[`fraction`](#fraction)

:   The fraction number.

[`group`](#group)

:   The group separator string (\",\").

[`infinity`](#infinity)

:   The [`Infinity`](../../infinity) string (\"∞\").

[`integer`](#integer)

:   The integer number.

[`literal`](#literal)

:   Any literal strings or whitespace in the formatted number.

[`minusSign`](#minussign)

:   The minus sign string (\"-\").

[`nan`](#nan)

:   The [`NaN`](../../nan) string (\"NaN\").

[`plusSign`](#plussign)

:   The plus sign string (\"+\").

[`percentSign`](#percentsign)

:   The percent sign string (\"%\").

[`unit`](#unit)

:   The unit string, such as the \"l\" or \"litres\", depending on how
    `unitDisplay` is specified.

Possible values for the `source` property include:

[`startRange`](#startrange_2)

:   The object is the start part of the range.

[`endRange`](#endrange_2)

:   The object is the end part of the range.

[`shared`](#shared)

:   The object is a \"shared\" part of the range, such as a separator or
    currency.



 
### Exceptions

 

[`RangeError`](../../rangeerror)

:   Thrown if `startRange` is less than `endRange`, or either value is
    `NaN`.

[`TypeError`](../../typeerror)

:   Thrown if either `startRange` or `endRange` is undefined.



 
Examples
--------


 
### Comparing formatRange and formatRangeToParts 

 
`NumberFormat` outputs localized, opaque strings that cannot be
manipulated directly:

 
 
[js]


```js
const startRange = 3500;
const endRange = 9500;

const formatter = new Intl.NumberFormat("de-DE", {
  style: "currency",
  currency: "EUR",
});

console.log(formatter.formatRange(startRange, endRange));
// "3.500,00–9.500,00 €"
```


However, for many user interfaces there is a need to customize the
formatting of this string. The `formatRangeToParts` method enables
locale-aware formatting of strings produced by `NumberFormat` formatters
by providing you the string in parts:

 
 
[js]


```js
console.log(formatter.formatRangeToParts(startRange, endRange));

// return value:
[
  { type: "integer", value: "3", source: "startRange" },
  { type: "group", value: ".", source: "startRange" },
  { type: "integer", value: "500", source: "startRange" },
  { type: "decimal", value: ",", source: "startRange" },
  { type: "fraction", value: "00", source: "startRange" },
  { type: "literal", value: "–", source: "shared" },
  { type: "integer", value: "9", source: "endRange" },
  { type: "group", value: ".", source: "endRange" },
  { type: "integer", value: "500", source: "endRange" },
  { type: "decimal", value: ",", source: "endRange" },
  { type: "fraction", value: "00", source: "endRange" },
  { type: "literal", value: " ", source: "shared" },
  { type: "currency", value: "€", source: "shared" },
];
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.numberformat.prototype.formatrangetoparts]](https://tc39.es/ecma402/#sec-intl.numberformat.prototype.formatrangetoparts)

  -------------------------------------------------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [`Intl.NumberFormat`](../numberformat)
-   [`Intl.NumberFormat.prototype.format()`](format)
-   [`Intl.DateTimeFormat.prototype.formatRangeToParts()`](../datetimeformat/formatrangetoparts)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/formatRangeToParts>

