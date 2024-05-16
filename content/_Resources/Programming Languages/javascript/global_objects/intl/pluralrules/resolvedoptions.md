Intl.PluralRules.prototype.resolvedOptions()
============================================

 
The `resolvedOptions()` method of [`Intl.PluralRules`](../pluralrules)
instances returns a new object with properties reflecting the locale and
plural formatting options computed during initialization of this
`Intl.PluralRules` object.


 
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

 
A new object with properties reflecting the locale and plural formatting
options computed during the initialization of the given
[`Intl.PluralRules`](../pluralrules) object.

The object has the following properties:

[`locale`](#locale)

:   The BCP 47 language tag for the locale actually used. If any Unicode
    extension values were requested in the input BCP 47 language tag
    that led to this locale, the key-value pairs that were requested and
    are supported for this locale are included in `locale`.

[`pluralCategories`](#pluralcategories)

:   An [`Array`](../../array) of plural categories used by the given
    locale, selected from the list `"zero"`, `"one"`, `"two"`, `"few"`,
    `"many"` and `"other"`.

[`type`](#type)

:   The type used (`cardinal` or `ordinal`).

[`roundingMode`](#roundingmode) [Experimental]

:   The rounding mode. This is the value provided for the
    [`options.roundingMode`](pluralrules#roundingmode) argument in the
    constructor, or the default value: `halfExpand`.

[`roundingPriority`](#roundingpriority) [Experimental]

:   The priority for resolving rounding conflicts if both
    \"FractionDigits\" and \"SignificantDigits\" are specified. This is
    the value provided for the
    [`options.roundingPriority`](pluralrules#roundingpriority) argument
    in the constructor, or the default value: `auto`.

[`roundingIncrement`](#roundingincrement) [Experimental]

:   The rounding-increment precision (the increment used when rounding
    numbers). This is the value specified in the
    [`options.roundingIncrement`](pluralrules#roundingincrement)
    argument in the constructor.

[`trailingZeroDisplay`](#trailingzerodisplay) [Experimental]

:   The strategy for displaying trailing zeros on whole numbers. This is
    the value specified in the
    [`options.trailingZeroDisplay`](pluralrules#trailingzerodisplay)
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


 
### Using the resolvedOptions() method 

 
The code below shows the construction of a `PluralRules` object,
followed by logging of each of the resolved options.

 
 
[js]


```js
// Create a PluralRules instance
const de = new Intl.PluralRules("de-DE", {
  maximumSignificantDigits: 2,
  trailingZeroDisplay: "auto",
});

// Resolve the options
const usedOptions = de.resolvedOptions();
console.log(usedOptions.locale); // "de-DE"
console.log(usedOptions.pluralCategories); // Array ["one", "other"]
console.log(usedOptions.type); // "cardinal"
console.log(usedOptions.minimumIntegerDigits); // 1
console.log(usedOptions.minimumFractionDigits); // undefined (maximumSignificantDigits is set)
console.log(usedOptions.maximumFractionDigits); //undefined (maximumSignificantDigits is set)
console.log(usedOptions.minimumSignificantDigits); // 1
console.log(usedOptions.maximumSignificantDigits); //2
console.log(usedOptions.roundingIncrement); // 1
console.log(usedOptions.roundingMode); // "halfExpand"
console.log(usedOptions.roundingPriority); // "auto"
console.log(usedOptions.trailingZeroDisplay); // "auto"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.pluralrules.prototype.resolvedoptions]](https://tc39.es/ecma402/#sec-intl.pluralrules.prototype.resolvedoptions)

  -----------------------------------------------------------------------------------------------------------------------------------


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

10.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `PluralRules()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/PluralRules/PluralRules)
for more details.

`result_roundingIncrement_property`

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

`result_roundingMode_property`

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

`result_roundingPriority_property`

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

`result_trailingZeroDisplay_property`

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



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/PluralRules/resolvedOptions>

