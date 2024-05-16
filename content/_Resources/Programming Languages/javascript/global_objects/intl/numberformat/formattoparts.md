Intl.NumberFormat.prototype.formatToParts()
===========================================

 
The `formatToParts()` method of [`Intl.NumberFormat`](../numberformat)
instances allows locale-aware formatting of strings produced by this
`Intl.NumberFormat` object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
formatToParts()
formatToParts(number)
```




 
### Parameters

 

[`number`](#number) [Optional]

:   A [`Number`](../../number) or [`BigInt`](../../bigint) to format.



 
### Return value 

 
An [`Array`](../../array) of objects containing the formatted number in
parts.



 
Description
-----------

 
The `formatToParts()` method is useful for custom formatting of number
strings. It returns an [`Array`](../../array) of objects containing the
locale-specific tokens from which it possible to build custom strings
while preserving the locale-specific parts. The structure the
`formatToParts()` method returns, looks like this:

 
 
[js]


```js
[
  { type: "integer", value: "3" },
  { type: "group", value: "." },
  { type: "integer", value: "500" },
];
```


Possible types are the following:

[`compact`](#compact)

:   The exponent in `"long"` or `"short"` form, depending on how
    `compactDisplay` (which defaults to `short`) is specified when
    `notation` is set to `compact`.

[`currency`](#currency)

:   The currency string, such as the symbols \"\$\" and \"€\" or the
    name \"Dollar\", \"Euro\", depending on how `currencyDisplay` is
    specified.

[`decimal`](#decimal)

:   The decimal separator string (\".\").

[`exponentInteger`](#exponentinteger)

:   The exponent integer value, when `notation` is set to `scientific`
    or `engineering`.

[`exponentMinusSign`](#exponentminussign)

:   The exponent minus sign string (\"-\").

[`exponentSeparator`](#exponentseparator)

:   The exponent separator, when `notation` is set to `scientific` or
    `engineering`.

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

[`unknown`](#unknown)

:   The string for `unknown` type results.



 
Examples
--------


 
### Comparing format and formatToParts 

 
`NumberFormat` outputs localized, opaque strings that cannot be
manipulated directly:

 
 
[js]


```js
const number = 3500;

const formatter = new Intl.NumberFormat("de-DE", {
  style: "currency",
  currency: "EUR",
});

formatter.format(number);
// "3.500,00 €"
```


However, in many User Interfaces there is a desire to customize the
formatting of this string. The `formatToParts` method enables
locale-aware formatting of strings produced by `NumberFormat` formatters
by providing you the string in parts:

 
 
[js]


```js
formatter.formatToParts(number);

// return value:
[
  { type: "integer", value: "3" },
  { type: "group", value: "." },
  { type: "integer", value: "500" },
  { type: "decimal", value: "," },
  { type: "fraction", value: "00" },
  { type: "literal", value: " " },
  { type: "currency", value: "€" },
];
```


Now the information is available separately and it can be formatted and
concatenated again in a customized way. For example by using
[`Array.prototype.map()`](../../array/map), [arrow
functions](../../../functions/arrow_functions), a [switch
statement](../../../statements/switch), [template
literals](../../../template_literals), and
[`Array.prototype.reduce()`](../../array/reduce).

 
 
[js]


```js
const numberString = formatter
  .formatToParts(number)
  .map(({ type, value }) => {
    switch (type) {
      case "currency":
        return `<strong>${value}</strong>`;
      default:
        return value;
    }
  })
  .reduce((string, part) => string + part);
```


This will make the currency bold, when using the `formatToParts()`
method.

 
 
[js]


```js
console.log(numberString);
// "3.500,00 <strong>€</strong>"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.numberformat.prototype.formattoparts]](https://tc39.es/ecma402/#sec-intl.numberformat.prototype.formattoparts)

  ---------------------------------------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [`Intl.NumberFormat`](../numberformat)
-   [`Intl.NumberFormat.prototype.format()`](format)
-   [`Intl.DateTimeFormat.prototype.formatToParts()`](../datetimeformat/formattoparts)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/formatToParts>

