Intl.NumberFormat.prototype.resolvedOptions()
=============================================

 
The `resolvedOptions()` method of [`Intl.NumberFormat`](../numberformat)
instances returns a new object with properties reflecting the [locale
and number formatting options](numberformat#parameters) computed during
initialization of this `Intl.NumberFormat` object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
resolvedOptions()
```




 
### Parameters

 
None.



 
### Return value 

 
A new object with properties reflecting the [locale and number
formatting options](numberformat#parameters) computed during the
construction of the given [`Intl.NumberFormat`](../numberformat) object.

The resulting object has the following properties:

[`compactDisplay`](#compactdisplay)

:   Whether to use short or long form when using compact notation. This
    is the value provided in the
    [`options.compactDisplay`](numberformat#compactdisplay) argument of
    the constructor, or the default value: `"short"`. The value is only
    present if `notation` is set to \"compact\", and otherwise is
    `undefined`.

[`currency`](#currency)

:   The currency to use in currency formatting. The value is defined if
    `style` is `"currency"`, and is otherwise `undefined`. This is the
    value provided in the [`options.currency`](numberformat#currency)
    argument of the constructor.

[`currencyDisplay`](#currencydisplay)

:   The display format for the currency, such as a symbol, or currency
    code. The value is defined if `style` is `"currency"`, and otherwise
    is `undefined`. This is the value provided in the
    [`options.currencyDisplay`](numberformat#currencydisplay) argument
    of the constructor, or the default value: `"symbol"`.

[`currencySign`](#currencysign)

:   The method used to specify the sign of the currency value:
    `standard` or `accounting`. The value is present if `style` is
    `"currency"`, and otherwise is `undefined`. This is the value
    provided in the [`options.currencySign`](numberformat#currencysign)
    argument of the constructor, or the default value: `"standard"`.

[`locale`](#locale)

:   The BCP 47 language tag for the locale that was actually used. The
    key-value pairs that were requested in the constructor
    [`locale`](numberformat#local) and are supported for this locale are
    included.

[`notation`](#notation)

:   The formatting that should be applied to the number, such as
    `standard` or `engineering`. This is the value provided in the
    [`options.notation`](numberformat#notation) argument of the
    constructor, or the default value: `"standard"`.

[`numberingSystem`](#numberingsystem)

:   The numbering system. This is the value provided in the
    [`options.numberingSystem`](numberformat#numberingsystem) argument
    of the constructor, if present, or the value set using the Unicode
    extension key [`nu`](numberformat#nu), or filled in as a default.

[`roundingMode`](#roundingmode)

:   The rounding mode. This is the value provided for the
    [`options.roundingMode`](numberformat#roundingmode) argument in the
    constructor, or the default value: `halfExpand`.

[`roundingPriority`](#roundingpriority)

:   The priority for resolving rounding conflicts if both
    \"FractionDigits\" and \"SignificantDigits\" are specified. This is
    the value provided for the
    [`options.roundingPriority`](numberformat#roundingpriority) argument
    in the constructor, or the default value: `auto`.

[`roundingIncrement`](#roundingincrement)

:   The rounding-increment precision (the increment used when rounding
    numbers). This is the value specified in the
    [`options.roundingIncrement`](numberformat#roundingincrement)
    argument in the constructor.

[`signDisplay`](#signdisplay)

:   Whether or not to display the positive/negative sign. This is the
    value specified in the
    [`options.signDisplay`](numberformat#signdisplay) argument in the
    constructor, or the default value: `"auto"`.

[`unit`](#unit)

:   The unit to use in unit formatting. The value is only present if
    `style` is `"unit"`, and is otherwise `undefined`. This is the value
    specified in the [`options.unit`](numberformat#unit) argument in the
    constructor.

[`unitDisplay`](#unitdisplay)

:   The display format to use for units in unit formatting, such as
    \"long\", \"short\" or \"narrow\". The value is only present if
    `style` is `"unit"`, and is otherwise `undefined`. This is the value
    specified in the [`options.unitDisplay`](numberformat#unitdisplay)
    argument in the constructor, or the default value: `short`.

[`useGrouping`](#usegrouping)

:   Whether or not to use grouping separators to indicate \"thousands\",
    \"millions\" and son on. This is the value specified in the
    [`options.useGrouping`](numberformat#usegrouping) argument in the
    constructor, or the default value: `"auto"`.

[`trailingZeroDisplay`](#trailingzerodisplay)

:   The strategy for displaying trailing zeros on whole numbers. This is
    the value specified in the
    [`options.trailingZeroDisplay`](numberformat#trailingzerodisplay)
    argument in the constructor, or the default value: `"auto"`.

Only one of the following two groups of properties is included:

[`minimumIntegerDigits`](#minimumintegerdigits), `minimumFractionDigits`, `maximumFractionDigits`

:   The values provided for these properties in the `options` argument
    or filled in as defaults. These properties are present only if
    neither `minimumSignificantDigits` nor `maximumSignificantDigits`
    was provided in the `options` argument.

[`minimumSignificantDigits`](#minimumsignificantdigits), `maximumSignificantDigits`

:   The values provided for these properties in the `options` argument
    or filled in as defaults. These properties are present only if at
    least one of them was provided in the `options` argument.



 
Examples
--------


 
### Using the `resolvedOptions` method 

 
 
 
[js]


```js
// Create a NumberFormat
const de = new Intl.NumberFormat("de-DE", {
  style: "currency",
  currency: "USD",
  maximumFractionDigits: 2,
  roundingIncrement: 5,
  roundingMode: "halfCeil",
});

// Resolve the options
const usedOptions = de.resolvedOptions();
console.log(usedOptions.locale); // "de-DE"
console.log(usedOptions.numberingSystem); // "latn"
console.log(usedOptions.compactDisplay); // undefined ("notation" not set to "compact")
console.log(usedOptions.currency); // "USD"
console.log(usedOptions.currencyDisplay); // "symbol"
console.log(usedOptions.currencySign); // "standard"
console.log(usedOptions.minimumIntegerDigits); // 1
console.log(usedOptions.minimumFractionDigits); // 2
console.log(usedOptions.maximumFractionDigits); // 2
console.log(usedOptions.minimumSignificantDigits); // undefined (maximumFractionDigits is set)
console.log(usedOptions.maximumSignificantDigits); // undefined (maximumFractionDigits is set)
console.log(usedOptions.notation); // "standard"
console.log(usedOptions.roundingIncrement); // 5
console.log(usedOptions.roundingMode); // halfCeil
console.log(usedOptions.roundingPriority); // auto
console.log(usedOptions.signDisplay); // "auto"
console.log(usedOptions.style); // "currency"
console.log(usedOptions.trailingZeroDisplay); // auto
console.log(usedOptions.useGrouping); // auto
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.numberformat.prototype.resolvedoptions]](https://tc39.es/ecma402/#sec-intl.numberformat.prototype.resolvedoptions)

  -------------------------------------------------------------------------------------------------------------------------------------


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

`result_roundingIncrement_property`

106

106

116

92

16.4

106

116

72

16.4

20.0

106

No

19.0.0

`result_roundingMode_property`

106

106

116

92

16.4

106

116

72

16.4

20.0

106

No

19.0.0

`result_roundingPriority_property`

106

106

116

92

16.4

106

116

72

16.4

20.0

106

No

19.0.0

`result_signDisplay_property`

106

106

116

92

16.4

106

116

72

16.4

20.0

106

No

19.0.0

`result_trailingZeroDisplay_property`

106

106

116

92

16.4

106

116

72

16.4

20.0

106

No

19.0.0

`result_useGrouping_property`

106

106

116

92

16.4

106

116

72

16.4

20.0

106

No

19.0.0

 
See also 
--------

 
-   [`Intl.NumberFormat`](../numberformat)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/resolvedOptions>

