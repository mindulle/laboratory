Intl.PluralRules
================

 
The `Intl.PluralRules` object enables plural-sensitive formatting and
plural-related language rules.


 
Description
-----------

 
Languages use different patterns for expressing both plural numbers of
items (cardinal numbers) and for expressing the order of items (ordinal
numbers). English has two forms for expressing cardinal numbers: one for
the singular \"item\" (1 hour, 1 dog, 1 fish) and the other for zero or
any other number of \"items\" (0 hours, 2 lemmings, 100000.5 fish),
while Chinese has only one form, and Arabic has six! Similarly, English
has four forms for expressing ordinal numbers: \"th\", \"st\", \"nd\",
\"rd\", giving the sequence: 0th, 1st, 2nd, 3rd, 4th, 5th, \..., 21st,
22nd, 23rd, 24th, 25th, and so on, while both Chinese and Arabic only
have one form for ordinal numbers.

Given a particular language and set of formatting options, the methods
[`Intl.PluralRules.prototype.select()`](pluralrules/select) and
[`Intl.PluralRules.prototype.selectRange()`](pluralrules/selectrange)
return a *tag* that represents the plural form of a single or a range of
numbers, cardinal or ordinal. Code can use the returned tags to
represent numbers appropriately for the given language. The full set of
tags that might be returned are: `zero`, `one`, `two`, `few`, `many`,
and `other` (the \"general\" plural form, also used if the language only
has one form).

As English only has two forms for cardinal numbers, the `select()`
method returns only two tags: `"one"` for the singular case, and
`"other"` for all other cardinal numbers. This allows construction of
sentences that make sense in English for each case, such as: \"1 dog is
happy; do you want to play with it?\" and \"10 dogs are happy; do you
want to play with them?\".

Creating appropriate sentences for each form depends on the language,
and even in English may not be as simple as just adding \"s\" to a noun
to make the plural form. Using the example above, we see that the form
may affect:

-   **Nouns**: 1 dogs/2 dogs (but not \"fish\" or \"sheep\", which have
    the same singular and plural form).
-   **Verbs**: 1 dog *is* happy, 2 dogs *are* happy
-   **Pronouns** (and other referents): Do you want to play with *it* /
    *them*.

Other languages have more forms, and choosing appropriate sentences can
be even more complex.

`select()` can return any of four tags for ordinal numbers in English,
representing each of the allowed forms: `one` for \"st\" numbers (1, 21,
31, \...), `two` for \"nd\" numbers (2, 22, 32, \...), `few` for \"rd\"
numbers (3, 33, 43, \...), and `other` for \"th\" numbers (0, 4-20,
etc.). Again, the returned tags allow appropriate formatting of strings
describing an ordinal number.

For more information about the rules and how they are used, see [Plural
Rules](https://cldr.unicode.org/index/cldr-spec/plural-rules). For a
list of the rules and how they apply for different languages, see the
[LDML Language Plural
Rules](https://www.unicode.org/cldr/charts/43/supplemental/language_plural_rules.html).



 
Constructor
-----------

 

[`Intl.PluralRules()`](pluralrules/pluralrules)

:   Creates a new `Intl.PluralRules` object.



 
Static methods 
--------------

 

[`Intl.PluralRules.supportedLocalesOf()`](pluralrules/supportedlocalesof)

:   Returns an array containing those of the provided locales that are
    supported without having to fall back to the runtime\'s default
    locale.



 
Instance properties 
-------------------

 
These properties are defined on `Intl.PluralRules.prototype` and shared
by all `Intl.PluralRules` instances.

[`Intl.PluralRules.prototype.constructor`](../object/constructor)

:   The constructor function that created the instance object. For
    `Intl.PluralRules` instances, the initial value is the
    [`Intl.PluralRules`](pluralrules/pluralrules) constructor.

[`Intl.PluralRules.prototype[@@toStringTag]`](#intl.pluralrules.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](../symbol/tostringtag)
    property is the string `"Intl.PluralRules"`. This property is used
    in [`Object.prototype.toString()`](../object/tostring).



 
Instance methods 
----------------

 

[`Intl.PluralRules.prototype.resolvedOptions()`](pluralrules/resolvedoptions)

:   Returns a new object with properties reflecting the locale and
    collation options computed during initialization of the object.

[`Intl.PluralRules.prototype.select()`](pluralrules/select)

:   Returns a string indicating which plural rule to use for
    locale-aware formatting.

[`Intl.PluralRules.prototype.selectRange()`](pluralrules/selectrange)

:   This method receives two values and returns a string indicating
    which plural rule to use for locale-aware formatting.



 
Examples
--------


 
### Using locales 

 
This example shows some of the variations in localized plural rules for
cardinal numbers.

In order to get the format for the language used in the user interface
of your application, make sure to specify that language (and possibly
some fallback languages) using the [constructor
`locales`](pluralrules/pluralrules#locales) argument:

 
 
[js]


```js
// US English
const enCardinalRules = new Intl.PluralRules("en-US");
console.log(enCardinalRules.select(0)); // "other"
console.log(enCardinalRules.select(1)); // "one"
console.log(enCardinalRules.select(2)); // "other"
console.log(enCardinalRules.select(3)); // "other"

// Arabic
const arCardinalRules = new Intl.PluralRules("ar-EG");
console.log(arCardinalRules.select(0)); // "zero"
console.log(arCardinalRules.select(1)); // "one"
console.log(arCardinalRules.select(2)); // "two"
console.log(arCardinalRules.select(6)); // "few"
console.log(arCardinalRules.select(18)); // "many"
```




 
### Using options 

 
The plural form of the specified number may also depend on [constructor
`options`](pluralrules/pluralrules#options), such as how the number is
rounded, and whether it is cardinal or ordinal.

This example shows how you can set the type of rules to \"ordinal\", and
how this affects the form for some numbers in US English.

 
 
[js]


```js
// US English - ordinal
const enOrdinalRules = new Intl.PluralRules("en-US", { type: "ordinal" });
console.log(enOrdinalRules.select(0)); // "other" (0th)
console.log(enOrdinalRules.select(1)); // "one"   (1st)
console.log(enOrdinalRules.select(2)); // "two"   (2nd)
console.log(enOrdinalRules.select(3)); // "few"   (3rd)
console.log(enOrdinalRules.select(4)); // "other" (4th)
console.log(enOrdinalRules.select(21)); // "one"  (21st)
```




 
### Formatting text using the returned tag 

 
The code below extends the previous example, showing how you might use
the returned tag for an ordinal number to format text in English.

 
 
[js]


```js
const enOrdinalRules = new Intl.PluralRules("en-US", { type: "ordinal" });

const suffixes = new Map([
  ["one", "st"],
  ["two", "nd"],
  ["few", "rd"],
  ["other", "th"],
]);
const formatOrdinals = (n) => {
  const rule = enOrdinalRules.select(n);
  const suffix = suffixes.get(rule);
  return `${n}${suffix}`;
};

formatOrdinals(0); // '0th'
formatOrdinals(1); // '1st'
formatOrdinals(2); // '2nd'
formatOrdinals(3); // '3rd'
formatOrdinals(4); // '4th'
formatOrdinals(11); // '11th'
formatOrdinals(21); // '21st'
formatOrdinals(42); // '42nd'
formatOrdinals(103); // '103rd'
```




Specifications
--------------

 
  -----------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  pluralrules-objects]](https://tc39.es/ecma402/#pluralrules-objects)

  -----------------------------------------------------------------------------


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

`PluralRules`

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

13.0.0

10.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. When other locales are specified, the
`PluralRules` instance silently falls back to `en-US`. To make full ICU
(locale) data available before version 13, see [Node.js documentation on
the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

`PluralRules`

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

`select`

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

`selectRange`

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

`supportedLocalesOf`

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

 
See also 
--------

 
-   [Polyfill of `Intl.PluralRules` in
    FormatJS](https://formatjs.io/docs/polyfills/intl-pluralrules/)
-   [`Intl`](../intl)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/PluralRules>

