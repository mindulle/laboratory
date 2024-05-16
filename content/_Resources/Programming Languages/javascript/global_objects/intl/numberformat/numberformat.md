Intl.NumberFormat() constructor
===============================

 
The `Intl.NumberFormat()` constructor creates
[`Intl.NumberFormat`](../numberformat) objects.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Intl.NumberFormat()
new Intl.NumberFormat(locales)
new Intl.NumberFormat(locales, options)

Intl.NumberFormat()
Intl.NumberFormat(locales)
Intl.NumberFormat(locales, options)
```


 
**Note:** `Intl.NumberFormat()` can be called with or without
[`new`](../../../operators/new). Both create a new `Intl.NumberFormat`
instance. However, there\'s a special behavior when it\'s called without
`new` and the `this` value is another `Intl.NumberFormat` instance; see
[Return value](#return_value).




 
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

:   An object. For ease of reading, the property list is broken into
    sections based on their purposes, including [locale
    options](#locale_options), [style options](#style_options), [digit
    options](#digit_options), and [other options](#other_options).

#### Locale options 

[`localeMatcher`](#localematcher)

:   The locale matching algorithm to use. Possible values are `"lookup"`
    and `"best fit"`; the default is `"best fit"`. For information about
    this option, see [Locale identification and
    negotiation](../../intl#locale_identification_and_negotiation).

[`numberingSystem`](#numberingsystem)

:   The numbering system to use for number formatting, such as `"arab"`,
    `"hans"`, `"mathsans"`, and so on. For a list of supported numbering
    system types, see
    [`Intl.Locale.prototype.getNumberingSystems()`](../locale/getnumberingsystems#supported_numbering_system_types).
    This option can also be set through the `nu` Unicode extension key;
    if both are provided, this `options` property takes precedence.

#### Style options 

Depending on the `style` used, some of them may be ignored, and others
may be required:

[`style`](#style)

:   The formatting style to use.

    [`"decimal"`](#decimal) (default)

    :   For plain number formatting.

    [`"currency"`](#currency)

    :   For currency formatting.

    [`"percent"`](#percent)

    :   For percent formatting.

    [`"unit"`](#unit)

    :   For unit formatting.

[`currency`](#currency_2)

:   The currency to use in currency formatting. Possible values are the
    ISO 4217 currency codes, such as `"USD"` for the US dollar, `"EUR"`
    for the euro, or `"CNY"` for the Chinese RMB --- see the [Current
    currency & funds code
    list](https://en.wikipedia.org/wiki/ISO_4217#List_of_ISO_4217_currency_codes).
    There is no default value; if the `style` is `"currency"`, the
    `currency` property must be provided.

[`currencyDisplay`](#currencydisplay)

:   How to display the currency in currency formatting.

    [`"code"`](#code)

    :   Use the ISO currency code.

    [`"symbol"`](#symbol) (default)

    :   Use a localized currency symbol such as €.

    [`"narrowSymbol"`](#narrowsymbol)

    :   Use a narrow format symbol (\"\$100\" rather than \"US\$100\").

    [`"name"`](#name)

    :   Use a localized currency name such as `"dollar"`.

[`currencySign`](#currencysign)

:   In many locales, accounting format means to wrap the number with
    parentheses instead of appending a minus sign. Possible values are
    `"standard"` and `"accounting"`; the default is `"standard"`.

[`unit`](#unit_2)

:   The unit to use in `unit` formatting, Possible values are core unit
    identifiers, defined in [UTS \#35, Part 2, Section
    6](https://unicode.org/reports/tr35/tr35-general.html#Unit_Elements).
    A
    [subset](https://tc39.es/ecma402/#table-sanctioned-single-unit-identifiers)
    of units from the [full
    list](https://github.com/unicode-org/cldr/blob/main/common/validity/unit.xml)
    was selected for use in ECMAScript. Pairs of simple units can be
    concatenated with \"-per-\" to make a compound unit. There is no
    default value; if the `style` is `"unit"`, the `unit` property must
    be provided.

[`unitDisplay`](#unitdisplay)

:   The unit formatting style to use in `unit` formatting. Possible
    values are:

    [`"short"`](#short) (default)

    :   E.g., `16 l`.

    [`"narrow"`](#narrow)

    :   E.g., `16l`.

    [`"long"`](#long)

    :   E.g., `16 litres`.

#### Digit options 

The following properties are also supported by
[`Intl.PluralRules`](../pluralrules).

[`minimumIntegerDigits`](#minimumintegerdigits)

:   The minimum number of integer digits to use. A value with a smaller
    number of integer digits than this number will be left-padded with
    zeros (to the specified length) when formatted. Possible values are
    from `1` to `21`; the default is `1`.

[`minimumFractionDigits`](#minimumfractiondigits)

:   The minimum number of fraction digits to use. Possible values are
    from `0` to `20`; the default for plain number and percent
    formatting is `0`; the default for currency formatting is the number
    of minor unit digits provided by the [ISO 4217 currency code
    list](https://www.six-group.com/dam/download/financial-information/data-center/iso-currrency/lists/list-one.xml)
    (2 if the list doesn\'t provide that information).

[`maximumFractionDigits`](#maximumfractiondigits)

:   The maximum number of fraction digits to use. Possible values are
    from `0` to `20`; the default for plain number formatting is the
    larger of `minimumFractionDigits` and `3`; the default for currency
    formatting is the larger of `minimumFractionDigits` and the number
    of minor unit digits provided by the [ISO 4217 currency code
    list](https://www.six-group.com/dam/download/financial-information/data-center/iso-currrency/lists/list-one.xml)
    (2 if the list doesn\'t provide that information); the default for
    percent formatting is the larger of `minimumFractionDigits` and 0.

[`minimumSignificantDigits`](#minimumsignificantdigits)

:   The minimum number of significant digits to use. Possible values are
    from `1` to `21`; the default is `1`.

[`maximumSignificantDigits`](#maximumsignificantdigits)

:   The maximum number of significant digits to use. Possible values are
    from `1` to `21`; the default is `21`.

The above properties fall into two groups: `minimumIntegerDigits`,
`minimumFractionDigits`, and `maximumFractionDigits` in one group,
`minimumSignificantDigits` and `maximumSignificantDigits` in the other.
If properties from both groups are specified, conflicts in the resulting
display format are resolved based on th value of the
[`roundingPriority`](#roundingpriority) property.

[`roundingPriority`](#roundingpriority)

:   Specify how rounding conflicts will be resolved if both
    \"FractionDigits\"
    ([`minimumFractionDigits`](#minimumfractiondigits)/[`maximumFractionDigits`](#maximumfractiondigits))
    and \"SignificantDigits\"
    ([`minimumSignificantDigits`](#minimumsignificantdigits)/[`maximumSignificantDigits`](#maximumsignificantdigits))
    are specified. Possible values are:

    [`"auto"`](#auto) (default)

    :   The result from the significant digits property is used.

    [`"morePrecision"`](#moreprecision)

    :   The result from the property that results in more precision is
        used.

    [`"lessPrecision"`](#lessprecision)

    :   The result from the property that results in less precision is
        used.

    Note that for values other than `auto` the result with more
    precision is calculated from the
    [`maximumSignificantDigits`](#minimumsignificantdigits) and
    [`maximumFractionDigits`](#maximumfractiondigits) (minimum
    fractional and significant digit settings are ignored).

[`roundingIncrement`](#roundingincrement)

:   Indicates the increment at which rounding should take place relative
    to the calculated rounding magnitude. Possible values are `1`, `2`,
    `5`, `10`, `20`, `25`, `50`, `100`, `200`, `250`, `500`, `1000`,
    `2000`, `2500`, and `5000`. It cannot be mixed with
    significant-digits rounding or any setting of `roundingPriority`
    other than `auto`.

[`roundingMode`](#roundingmode)

:   How decimals should be rounded. Possible values are:

    [`"ceil"`](#ceil)

    :   Round toward +∞. Positive values round up. Negative values round
        \"more positive\".

    [`"floor"`](#floor)

    :   Round toward -∞. Positive values round down. Negative values
        round \"more negative\".

    [`"expand"`](#expand)

    :   round away from 0. The *magnitude* of the value is always
        increased by rounding. Positive values round up. Negative values
        round \"more negative\".

    [`"trunc"`](#trunc)

    :   Round toward 0. This *magnitude* of the value is always reduced
        by rounding. Positive values round down. Negative values round
        \"less negative\".

    [`"halfCeil"`](#halfceil)

    :   ties toward +∞. Values above the half-increment round like
        `"ceil"` (towards +∞), and below like `"floor"` (towards -∞). On
        the half-increment, values round like `"ceil"`.

    [`"halfFloor"`](#halffloor)

    :   Ties toward -∞. Values above the half-increment round like
        `"ceil"` (towards +∞), and below like `"floor"` (towards -∞). On
        the half-increment, values round like `"floor"`.

    [`"halfExpand"`](#halfexpand) (default)

    :   Ties away from 0. Values above the half-increment round like
        `"expand"` (away from zero), and below like `"trunc"` (towards
        0). On the half-increment, values round like `"expand"`.

    [`"halfTrunc"`](#halftrunc)

    :   Ties toward 0. Values above the half-increment round like
        `"expand"` (away from zero), and below like `"trunc"` (towards
        0). On the half-increment, values round like `"trunc"`.

    [`"halfEven"`](#halfeven)

    :   Ties towards the nearest even integer. Values above the
        half-increment round like `"expand"` (away from zero), and below
        like `"trunc"` (towards 0). On the half-increment values round
        towards the nearest even digit.

    These options reflect the [ICU user
    guide](https://unicode-org.github.io/icu/userguide/format_parse/numbers/rounding-modes.html),
    where \"expand\" and \"trunc\" map to ICU \"UP\" and \"DOWN\",
    respectively. The [rounding modes](#rounding_modes) example below
    demonstrates how each mode works.

[`trailingZeroDisplay`](#trailingzerodisplay)

:   The strategy for displaying trailing zeros on whole numbers.
    Possible values are:

    [`"auto"`](#auto_2) (default)

    :   Keep trailing zeros according to `minimumFractionDigits` and
        `minimumSignificantDigits`.

    [`"stripIfInteger"`](#stripifinteger)

    :   Remove the fraction digits *if* they are all zero. This is the
        same as `"auto"` if any of the fraction digits is non-zero.

#### Other options 

[`notation`](#notation)

:   The formatting that should be displayed for the number. Possible
    values are:

    [`"standard"`](#standard) (default)

    :   Plain number formatting.

    [`"scientific"`](#scientific)

    :   Return the order-of-magnitude for formatted number.

    [`"engineering"`](#engineering)

    :   Return the exponent of ten when divisible by three.

    [`"compact"`](#compact)

    :   String representing exponent; defaults to using the \"short\"
        form.

[`compactDisplay`](#compactdisplay)

:   Only used when `notation` is `"compact"`. Possible values are
    `"short"` and `"long"`; the default is `"short"`.

[`useGrouping`](#usegrouping)

:   Whether to use grouping separators, such as thousands separators or
    thousand/lakh/crore separators.

    [`"always"`](#always)

    :   Display grouping separators even if the locale prefers
        otherwise.

    [`"auto"`](#auto_3)

    :   Display grouping separators based on the locale preference,
        which may also be dependent on the currency.

    [`"min2"`](#min2)

    :   Display grouping separators when there are at least 2 digits in
        a group.

    [`true`](#true)

    :   Same as `"always"`.

    [`false`](#false)

    :   Display no grouping separators.

    The default is `"min2"` if `notation` is `"compact"`, and `"auto"`
    otherwise. The string values `"true"` and `"false"` are accepted,
    but are always converted to the default value.

[`signDisplay`](#signdisplay)

:   When to display the sign for the number. Possible values are:

    [`"auto"`](#auto_4) (default)

    :   Sign display for negative numbers only, including negative zero.

    [`"always"`](#always_2)

    :   Always display sign.

    [`"exceptZero"`](#exceptzero)

    :   Sign display for positive and negative numbers, but not zero.

    [`"negative"`](#negative)

    :   Sign display for negative numbers only, excluding negative zero.

    [`"never"`](#never)

    :   Never display sign.



 
### Return value 

 
A new `Intl.NumberFormat` object.

 
**Note:** The text below describes behavior that is marked by the
specification as \"optional\". It may not work in all environments.
Check the [browser compatibility table](#browser_compatibility).


Normally, `Intl.NumberFormat()` can be called with or without
[`new`](../../../operators/new), and a new `Intl.NumberFormat` instance
is returned in both cases. However, if the
[`this`](../../../operators/this) value is an object that is
[`instanceof`](../../../operators/instanceof) `Intl.NumberFormat`
(doesn\'t necessarily mean it\'s created via `new Intl.NumberFormat`;
just that it has `Intl.NumberFormat.prototype` in its prototype chain),
then the value of `this` is returned instead, with the newly created
`Intl.NumberFormat` object hidden in a
`[Symbol(IntlLegacyConstructedSymbol)]` property (a unique symbol
that\'s reused between instances).

 
 
[js]


```js
const formatter = Intl.NumberFormat.call(
  { __proto__: Intl.NumberFormat.prototype },
  "en-US",
  { notation: "scientific" },
);
console.log(Object.getOwnPropertyDescriptors(formatter));
// {
//   [Symbol(IntlLegacyConstructedSymbol)]: {
//     value: NumberFormat [Intl.NumberFormat] {},
//     writable: false,
//     enumerable: false,
//     configurable: false
//   }
// }
```


Note that there\'s only one actual `Intl.NumberFormat` instance here:
the one hidden in `[Symbol(IntlLegacyConstructedSymbol)]`. Calling the
[`format()`](format) and [`resolvedOptions()`](resolvedoptions) methods
on `formatter` would correctly use the options stored in that instance,
but calling all other methods (e.g. [`formatRange()`](formatrange))
would fail with \"TypeError: formatRange method called on incompatible
Object\", because those methods don\'t consult the hidden instance\'s
options.

This behavior, called `ChainNumberFormat`, does not happen when
`Intl.NumberFormat()` is called without `new` but with `this` set to
anything else that\'s not an `instanceof Intl.NumberFormat`. If you call
it directly as `Intl.NumberFormat()`, the `this` value is
[`Intl`](../../intl), and a new `Intl.NumberFormat` instance is created
normally.



 
### Exceptions

 

[`RangeError`](../../rangeerror)

:   Thrown in one of the following cases:

    -   A property that takes enumerated values (such as `style`,
        `units`, `currency`, and so on) is set to an invalid value.
    -   Both `maximumFractionDigits` and `minimumFractionDigits` are
        set, and they are set to different values. Note that depending
        on various formatting options, these properties can have default
        values. It is therefore possible to get this error even if you
        only set one of the properties.

[`TypeError`](../../typeerror)

:   Thrown if the `options.style` property is set to \"unit\" or
    \"currency\", and no value has been set for the corresponding
    property `options.unit` or `options.currency`.



 
Examples
--------


 
### Basic usage 

 
In basic use without specifying a locale, a formatted string in the
default locale and with default options is returned.

 
 
[js]


```js
const amount = 3500;

console.log(new Intl.NumberFormat().format(amount));
// '3,500' if in US English locale
```




 
### Decimal and percent formatting 

 
 
 
[js]


```js
const amount = 3500;

new Intl.NumberFormat("en-US", {
  style: "decimal",
}).format(amount); // '3,500'
new Intl.NumberFormat("en-US", {
  style: "percent",
}).format(amount); // '350,000%'
```




 
### Unit formatting 

 
If the `style` is `'unit'`, a `unit` property must be provided.
Optionally, `unitDisplay` controls the unit formatting.

 
 
[js]


```js
const amount = 3500;

new Intl.NumberFormat("en-US", {
  style: "unit",
  unit: "liter",
}).format(amount); // '3,500 L'

new Intl.NumberFormat("en-US", {
  style: "unit",
  unit: "liter",
  unitDisplay: "long",
}).format(amount); // '3,500 liters'
```




 
### Currency formatting 

 
If the `style` is `'currency'`, a `currency` property must be provided.
Optionally, `currencyDisplay` and `currencySign` control the unit
formatting.

 
 
[js]


```js
const amount = -3500;
new Intl.NumberFormat("en-US", {
  style: "currency",
  currency: "USD",
}).format(amount); // '-$3,500.00'

new Intl.NumberFormat("bn", {
  style: "currency",
  currency: "USD",
  currencyDisplay: "name",
}).format(amount); // '-3,500.00 US dollars'

new Intl.NumberFormat("bn", {
  style: "currency",
  currency: "USD",
  currencySign: "accounting",
}).format(amount); // '($3,500.00)'
```




 
### Scientific, engineering or compact notations 

 
Scientific and compact notation are represented by the `notation` option
and can be formatted like this:

 
 
[js]


```js
new Intl.NumberFormat("en-US", {
  notation: "scientific",
}).format(987654321);
// 9.877E8

new Intl.NumberFormat("pt-PT", {
  notation: "scientific",
}).format(987654321);
// 9,877E8

new Intl.NumberFormat("en-GB", {
  notation: "engineering",
}).format(987654321);
// 987.654E6

new Intl.NumberFormat("de", {
  notation: "engineering",
}).format(987654321);
// 987,654E6

new Intl.NumberFormat("zh-CN", {
  notation: "compact",
}).format(987654321);
// 9.9亿

new Intl.NumberFormat("fr", {
  notation: "compact",
  compactDisplay: "long",
}).format(987654321);
// 988 millions

new Intl.NumberFormat("en-GB", {
  notation: "compact",
  compactDisplay: "short",
}).format(987654321);
// 988M
```




 
### Displaying signs 

 
Display a sign for positive and negative numbers, but not zero:

 
 
[js]


```js
new Intl.NumberFormat("en-US", {
  style: "percent",
  signDisplay: "exceptZero",
}).format(0.55);
// '+55%'
```


Note that when the currency sign is \"accounting\", parentheses might be
used instead of a minus sign:

 
 
[js]


```js
new Intl.NumberFormat("bn", {
  style: "currency",
  currency: "USD",
  currencySign: "accounting",
  signDisplay: "always",
}).format(-3500);
// '($3,500.00)'
```




 
### FractionDigits, SignificantDigits and IntegerDigits 

 
You can specify the minimum or maximum number of fractional, integer or
significant digits to display when formatting a number.

 
**Note:** If both significant and fractional digit limits are specified,
then the actual formatting depends on the
[`roundingPriority`](#roundingpriority).


#### Using FractionDigits and IntegerDigits 

The integer and fraction digit properties indicate the number of digits
to display before and after the decimal point, respectively. If the
value to display has fewer integer digits than specified, it will be
left-padded with zeros to the expected number. If it has fewer
fractional digits, it will be right-padded with zeros. Both cases are
shown below:

 
 
[js]


```js
// Formatting adds zeros to display minimum integers and fractions
console.log(
  new Intl.NumberFormat("en", {
    minimumIntegerDigits: 3,
    minimumFractionDigits: 4,
  }).format(4.33),
);
// "004.3300"
```


If a value has more fractional digits than the specified maximum number,
it will be rounded. The *way* that it is rounded depends on the
[`roundingMode`](#roundingmode) property (more details are provided in
the [rounding modes](#rounding_modes) section). Below the value is
rounded from five fractional digits (`4.33145`) to two (`4.33`):

 
 
[js]


```js
// Display value shortened to maximum number of digits
console.log(
  new Intl.NumberFormat("en", {
    maximumFractionDigits: 2,
  }).format(4.33145),
);
// "4.33"
```


The minimum fractional digits have no effect if the value already has
more than 2 fractional digits:

 
 
[js]


```js
// Minimum fractions have no effect if value is higher precision.
console.log(
  new Intl.NumberFormat("en", {
    minimumFractionDigits: 2,
  }).format(4.33145),
);
// "4.331"
```


 
**Warning:** Watch out for default values as they may affect formatting
even if not specified in your code. The default maximum digit value is
`3` for plain values, `2` for currency, and may have different values
for other predefined types.


The formatted value above is rounded to 3 digits, even though we didn\'t
specify the maximum digits! This is because a default value of
`maximumFractionDigits` is set when we specify `minimumFractionDigits`,
and visa versa. The default values of `maximumFractionDigits` and
`minimumFractionDigits` are `3` and `0`, respectively.

You can use [`resolvedOptions()`](resolvedoptions) to inspect the
formatter.

 
 
[js]


```js
console.log(
  new Intl.NumberFormat("en", {
    maximumFractionDigits: 2,
  }).resolvedOptions(),
);
// {
//   …
//   minimumIntegerDigits: 1,
//   minimumFractionDigits: 0,
//   maximumFractionDigits: 2,
//   …
// }

console.log(
  new Intl.NumberFormat("en", {
    minimumFractionDigits: 2,
  }).resolvedOptions(),
);
// {
//   …
//   minimumIntegerDigits: 1,
//   minimumFractionDigits: 2,
//   maximumFractionDigits: 3,
//   …
// }
```


#### Using SignificantDigits 

The number of *significant digits* is the total number of digits
including both integer and fractional parts. The
`maximumSignificantDigits` is used to indicate the total number of
digits from the original value to display.

The examples below show how this works. Note in particular the last
case: only the first digit is retained and the others are discarded/set
to zero.

 
 
[js]


```js
// Display 5 significant digits
console.log(
  new Intl.NumberFormat("en", {
    maximumSignificantDigits: 5,
  }).format(54.33145),
);
// "54.331"

// Max 2 significant digits
console.log(
  new Intl.NumberFormat("en", {
    maximumSignificantDigits: 2,
  }).format(54.33145),
);
// "54"

// Max 1 significant digits
console.log(
  new Intl.NumberFormat("en", {
    maximumSignificantDigits: 1,
  }).format(54.33145),
);
// "50"
```


The `minimumSignificantDigits` ensures that at least the specified
number of digits are displayed, adding zeros to the end of the value if
needed.

 
 
[js]


```js
// Minimum 10 significant digits
console.log(
  new Intl.NumberFormat("en", {
    minimumSignificantDigits: 10,
  }).format(54.33145),
);
// "54.33145000"
```


 
**Warning:** Watch out for default values as they may affect formatting.
If only one `SignificantDigits` property is used, then its counterpart
will automatically be applied with the default value. The default
maximum and minimum significant digit values are 20 and 1, respectively.


#### Specifying significant and fractional digits at the same time 

The fraction digits
([`minimumFractionDigits`](#minimumfractiondigits)/[`maximumFractionDigits`](#maximumfractiondigits))
and significant digits
([`minimumSignificantDigits`](#minimumsignificantdigits)/[`maximumSignificantDigits`](#maximumsignificantdigits))
are both ways of controlling how many fractional and leading digits
should be formatted. If both are used at the same time, it is possible
for them to conflict.

These conflicts are resolved using the
[`roundingPriority`](#roundingpriority) property. By default, this has a
value of `"auto"`, which means that if either
[`minimumSignificantDigits`](#minimumsignificantdigits) or
[`maximumSignificantDigits`](#minimumsignificantdigits) is specified,
the fractional and integer digit properties will be ignored.

For example, the code below formats the value of `4.33145` with
`maximumFractionDigits: 3`, and then `maximumSignificantDigits: 2`, and
then both. The value with both is the one set with
`maximumSignificantDigits`.

 
 
[js]


```js
console.log(
  new Intl.NumberFormat("en", {
    maximumFractionDigits: 3,
  }).format(4.33145),
);
// "4.331"
console.log(
  new Intl.NumberFormat("en", {
    maximumSignificantDigits: 2,
  }).format(4.33145),
);
// "4.3"
console.log(
  new Intl.NumberFormat("en", {
    maximumFractionDigits: 3,
    maximumSignificantDigits: 2,
  }).format(4.33145),
);
// "4.3"
```


Using [`resolvedOptions()`](resolvedoptions) to inspect the formatter,
we can see that the returned object does not include
`maximumFractionDigits` when `maximumSignificantDigits` or
`minimumSignificantDigits` are specified.

 
 
[js]


```js
console.log(
  new Intl.NumberFormat("en", {
    maximumFractionDigits: 3,
    maximumSignificantDigits: 2,
  }).resolvedOptions(),
);
// {
//   …
//   minimumIntegerDigits: 1,
//   minimumSignificantDigits: 1,
//   maximumSignificantDigits: 2,
//   …
// }
console.log(
  new Intl.NumberFormat("en", {
    maximumFractionDigits: 3,
    minimumSignificantDigits: 2,
  }).resolvedOptions(),
);
// {
//   …
//   minimumIntegerDigits: 1,
//   minimumSignificantDigits: 2,
//   maximumSignificantDigits: 21,
//   …
// }
```


In addition to `"auto"`, you can resolve conflicts by specifying
[`roundingPriority`](#roundingpriority) as `"morePrecision"` or
`"lessPrecision"`. The formatter calculates the precision using the
values of `maximumSignificantDigits` and `maximumFractionDigits`.

The code below shows the format being selected for the three different
rounding priorities:

 
 
[js]


```js
const maxFracNF = new Intl.NumberFormat("en", {
  maximumFractionDigits: 3,
});
console.log(`maximumFractionDigits:3 - ${maxFracNF.format(1.23456)}`);
// "maximumFractionDigits:2 - 1.235"

const maxSigNS = new Intl.NumberFormat("en", {
  maximumSignificantDigits: 3,
});
console.log(`maximumSignificantDigits:3 - ${maxSigNS.format(1.23456)}`);
// "maximumSignificantDigits:3 - 1.23"

const bothAuto = new Intl.NumberFormat("en", {
  maximumSignificantDigits: 3,
  maximumFractionDigits: 3,
});
console.log(`auto - ${bothAuto.format(1.23456)}`);
// "auto - 1.23"

const bothLess = new Intl.NumberFormat("en", {
  roundingPriority: "lessPrecision",
  maximumSignificantDigits: 3,
  maximumFractionDigits: 3,
});
console.log(`lessPrecision - ${bothLess.format(1.23456)}`);
// "lessPrecision - 1.23"

const bothMore = new Intl.NumberFormat("en", {
  roundingPriority: "morePrecision",
  maximumSignificantDigits: 3,
  maximumFractionDigits: 3,
});
console.log(`morePrecision - ${bothMore.format(1.23456)}`);
// "morePrecision - 1.235"
```


Note that the algorithm can behave in an unintuitive way if a minimum
value is specified without a maximum value. The example below formats
the value `1` specifying `minimumFractionDigits: 2` (formatting to
`1.00`) and `minimumSignificantDigits: 2` (formatting to `1.0`). Since
`1.00` has more digits than `1.0`, this should be the result when
prioritizing `morePrecision`, but in fact the opposite is true:

 
 
[js]


```js
const bothLess = new Intl.NumberFormat("en", {
  roundingPriority: "lessPrecision",
  minimumFractionDigits: 2,
  minimumSignificantDigits: 2,
});
console.log(`lessPrecision - ${bothLess.format(1)}`);
// "lessPrecision - 1.00"

const bothMore = new Intl.NumberFormat("en", {
  roundingPriority: "morePrecision",
  minimumFractionDigits: 2,
  minimumSignificantDigits: 2,
});
console.log(`morePrecision - ${bothMore.format(1)}`);
// "morePrecision - 1.0"
```


The reason for this is that only the \"maximum precision\" values are
used for the calculation, and the default value of
`maximumSignificantDigits` is much higher than `maximumFractionDigits`.

 
**Note:** The working group have proposed a modification of the
algorithm where the formatter should evaluate the result of using the
specified fractional and significant digits independently (taking
account of both minimum and maximum values). It will then select the
option that displays more fractional digits if `morePrecision` is set,
and fewer if `lessPrecision` is set. This will result in more intuitive
behavior for this case.




 
### Rounding modes 

 
If a value has more fractional digits than allowed by the constructor
options, the formatted value will be *rounded* to the specified number
of fractional digits. The *way* in which the value is rounded depends on
the [`roundingMode`](#roundingmode) property.

Number formatters use `halfExpand` rounding by default, which rounds
values \"away from zero\" at the half-increment (in other words, the
*magnitude* of the value is rounded up).

For a positive number, if the fractional digits to be removed are closer
to the next increment (or on the half way point) then the remaining
fractional digits will be rounded up, otherwise they are rounded down.
This is shown below: 2.23 rounded to two significant digits is truncated
to 2.2 because 2.23 is less than the half increment 2.25, while values
of 2.25 and greater are rounded up to 2.3:

 
 
[js]


```js
// Value below half-increment: round down.
console.log(
  new Intl.NumberFormat("en", {
    maximumSignificantDigits: 2,
  }).format(2.23),
);
// "2.2"

// Value on or above half-increment: round up.
console.log(
  new Intl.NumberFormat("en", {
    maximumSignificantDigits: 2,
  }).format(2.25),
);
console.log(
  new Intl.NumberFormat("en", {
    maximumSignificantDigits: 2,
  }).format(2.28),
);
// "2.3"
// "2.3"
```


A negative number on or below the half-increment point is also rounded
away from zero (becomes more negative):

 
 
[js]


```js
// Value below half-increment: round down.
console.log(
  new Intl.NumberFormat("en", {
    maximumSignificantDigits: 2,
  }).format(-2.23),
);
// "-2.2"

// Value on or above half-increment: round up.
console.log(
  new Intl.NumberFormat("en", {
    maximumSignificantDigits: 2,
  }).format(-2.25),
);
console.log(
  new Intl.NumberFormat("en", {
    maximumSignificantDigits: 2,
  }).format(-2.28),
);
// "-2.3"
// "-2.3"
```


The table below show the effect of different rounding modes for positive
and negative values that are on and around the half-increment.

 
  rounding mode   2.23   2.25   2.28   -2.23   -2.25   -2.28
  --------------- ------ ------ ------ ------- ------- -------
  `ceil`          2.3    2.3    2.3    -2.2    -2.2    -2.2
  `floor`         2.2    2.2    2.2    -2.3    -2.3    -2.3
  `expand`        2.3    2.3    2.3    -2.3    -2.3    -2.3
  `trunc`         2.2    2.2    2.2    -2.2    -2.2    -2.2
  `halfCeil`      2.2    2.3    2.3    -2.2    -2.2    -2.3
  `halfFloor`     2.2    2.2    2.3    -2.2    -2.3    -2.3
  `halfExpand`    2.2    2.3    2.3    -2.2    -2.3    -2.3
  `halfTrunc`     2.2    2.2    2.3    -2.2    -2.2    -2.3
  `halfEven`      2.2    2.2    2.3    -2.2    -2.2    -2.3


When using `halfEven`, its behavior also depends on the parity (odd or
even) of the last digit of the rounded number. For example, the behavior
of `halfEven` in the table above is the same as `halfTrunc`, because the
magnitudes of all numbers are between a smaller \"even\" number (2.2)
and a larger \"odd\" number (2.3). If the numbers are between ±2.3 and
±2.4, `halfEven` will behave like `halfExpand` instead. This behavior
avoids consistently under- or over-estimating half-increments in a large
data sample.



 
### Using roundingIncrement 

 
Sometimes we want to round the remaining fractional digits to some other
increment than the next integer. For example, currencies for which the
smallest coin is 5 cents might want to round the value to increments of
5, reflecting amounts that can actually be paid in cash.

This kind of rounding can be achieved with the
[`roundingIncrement`](#roundingincrement) property.

For example, if `maximumFractionDigits` is 2 and `roundingIncrement` is
5, then the number is rounded to the nearest 0.05:

 
 
[js]


```js
const nf = new Intl.NumberFormat("en-US", {
  style: "currency",
  currency: "USD",
  maximumFractionDigits: 2,
  roundingIncrement: 5,
});

console.log(nf.format(11.29)); // "$11.30"
console.log(nf.format(11.25)); // "$11.25"
console.log(nf.format(11.22)); // "$11.20"
```


This particular pattern is referred to as \"nickel rounding\", where
nickel is the colloquial name for a USA 5 cent coin. To round to the
nearest 10 cents (\"dime rounding\"), you could change
`roundingIncrement` to `10`.

 
 
[js]


```js
const nf = new Intl.NumberFormat("en-US", {
  style: "currency",
  currency: "USD",
  maximumFractionDigits: 2,
  roundingIncrement: 5,
});

console.log(nf.format(11.29)); // "$11.30"
console.log(nf.format(11.25)); // "$11.25"
console.log(nf.format(11.22)); // "$11.20"
```


You can also use [`roundingMode`](#roundingmode) to change the rounding
algorithm. The example below shows how `halfCeil` rounding can be used
to round the value \"less positive\" below the half-rounding increment
and \"more positive\" if above or on the half-increment. The incremented
digit is \"0.05\" so the half-increment is at .025 (below, this is shown
at 11.225).

 
 
[js]


```js
const nf = new Intl.NumberFormat("en-US", {
  style: "currency",
  currency: "USD",
  maximumFractionDigits: 2,
  roundingIncrement: 5,
  roundingMode: "halfCeil",
});

console.log(nf.format(11.21)); // "$11.20"
console.log(nf.format(11.22)); // "$11.20"
console.log(nf.format(11.224)); // "$11.20"
console.log(nf.format(11.225)); // "$11.25"
console.log(nf.format(11.23)); // "$11.25"
```


If you need to change the number of digits, remember that
`minimumFractionDigits` and `maximumFractionDigits` must both be set to
the same value, or a `RangeError` is thrown.

`roundingIncrement` cannot be mixed with significant-digits rounding or
any setting of `roundingPriority` other than `auto`.



Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl-numberformat-constructor]](https://tc39.es/ecma402/#sec-intl-numberformat-constructor)

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

`IntlLegacyConstructedSymbol`

91

57The fallback symbol property has description `IntlFallback`.

91

79The fallback symbol property has description `IntlFallback`.

54

77

44The fallback symbol property has description `IntlFallback`.

14.1

91

57The fallback symbol property has description `IntlFallback`.

56

64

43The fallback symbol property has description `IntlFallback`.

14.5

16.0

7.0The fallback symbol property has description `IntlFallback`.

91

57The fallback symbol property has description `IntlFallback`.

?

16.0.0

8.0.0The fallback symbol property has description `IntlFallback`.

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

`locales_parameter`

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
available by default. When other locales are specified, the
`NumberFormat` instance silently falls back to `en-US`. To make full ICU
(locale) data available before version 13, see [Node.js documentation on
the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

`options_compactDisplay_parameter`

77

79

78

64

14.1

77

79

55

14.5

12.0

77

1.8

12.11.0

`options_currencyDisplay_parameter`

77

79

78

64

14.1

10--14.1Doesn\'t support `currencyDisplay: 'narrowSymbol'`.

77

79

55

14.5

10--14.5Doesn\'t support `currencyDisplay: 'narrowSymbol'`.

12.0

77

1.8

12.11.0

`options_currencySign_parameter`

77

79

78

64

14.1

77

79

55

14.5

12.0

77

1.8

12.11.0

`options_currency_parameter`

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

`options_localeMatcher_parameter`

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

`options_maximumFractionDigits_parameter`

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

`options_maximumSignificantDigits_parameter`

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

`options_minimumFractionDigits_parameter`

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

`options_minimumIntegerDigits_parameter`

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

`options_minimumSignificantDigits_parameter`

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

`options_notation_parameter`

77

79

78

64

14.1

77

79

55

14.5

12.0

77

1.8

12.11.0

`options_numberingSystem_parameter`

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

`options_roundingIncrement_parameter`

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

`options_roundingMode_parameter`

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

`options_roundingPriority_parameter`

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

`options_signDisplay_parameter`

77

79

78

64

14.1

77

79

55

14.5

12.0

77

1.8

12.11.0

`options_style_parameter`

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

`options_trailingZeroDisplay_parameter`

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

`options_unitDisplay_parameter`

77

79

78

64

14.1

77

79

55

14.5

12.0

77

1.8

12.11.0

`options_unit_parameter`

77

79

78

64

14.1

77

79

55

14.5

12.0

77

1.8

12.11.0

`options_useGrouping_parameter`

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
available by default. When other locales are specified, the
`NumberFormat` instance silently falls back to `en-US`. To make full ICU
(locale) data available before version 13, see [Node.js documentation on
the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

 
See also 
--------

 
-   [`Intl.NumberFormat`](../numberformat)
-   [`Intl.supportedValuesOf()`](../supportedvaluesof)
-   [`Intl`](../../intl)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/NumberFormat>

