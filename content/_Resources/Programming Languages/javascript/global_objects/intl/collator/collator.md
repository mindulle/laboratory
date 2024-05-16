Intl.Collator() constructor
===========================

 
The `Intl.Collator()` constructor creates [`Intl.Collator`](../collator)
objects.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Intl.Collator()
new Intl.Collator(locales)
new Intl.Collator(locales, options)

Intl.Collator()
Intl.Collator(locales)
Intl.Collator(locales, options)
```


 
**Note:** `Intl.Collator()` can be called with or without
[`new`](../../../operators/new). Both create a new `Intl.Collator`
instance.




 
### Parameters

 

[`locales`](#locales) [Optional]

:   A string with a BCP 47 language tag or an [`Intl.Locale`](../locale)
    instance, or an array of such locale identifiers. For the general
    form and interpretation of the `locales` argument, see [the
    parameter description on the `Intl` main
    page](../../intl#locales_argument).

    The following Unicode extension keys are allowed:

    [`co`](#co)

    :   See [`collation`](#collation).

    [`kn`](#kn)

    :   See [`numeric`](#numeric).

    [`kf`](#kf)

    :   See [`caseFirst`](#casefirst).

    These keys can also be set with `options` (as listed below). When
    both are set, the `options` property takes precedence.

[`options`](#options) [Optional]

:   An object containing the following properties, in the order they are
    retrieved (all of them are optional):

    [`usage`](#usage)

    :   Whether the comparison is for sorting a list of strings or fuzzy
        (for the Latin script diacritic-insensitive and
        case-insensitive) filtering a list of strings by key. Possible
        values are:

        [`"sort"`](#sort) (default)

        :   For sorting a list of strings.

        [`"search"`](#search)

        :   For filtering a list of strings by testing each list item
            for a full-string match against a key. With `"search"`, the
            caller should only pay attention to whether `compare()`
            returns zero or non-zero and should not distinguish the
            non-zero return values from each other. That is, it is
            inappropriate to use `"search"` for sorting/ordering.

    [`localeMatcher`](#localematcher)

    :   The locale matching algorithm to use. Possible values are
        `"lookup"` and `"best fit"`; the default is `"best fit"`. For
        information about this option, see [Locale identification and
        negotiation](../../intl#locale_identification_and_negotiation).

    [`collation`](#collation)

    :   Variant collations for certain locales, such as `"emoji"`,
        `"pinyin"`, `"stroke"`, and so on. For a list of supported
        collation types, see
        [`Intl.Locale.prototype.getCollations()`](../locale/getcollations#supported_collation_types);
        the default is `"default"`. This option can also be set through
        the `co` Unicode extension key; if both are provided, this
        `options` property takes precedence.

    [`numeric`](#numeric)

    :   Whether numeric collation should be used, such that \"1\" \<
        \"2\" \< \"10\". Possible values are `true` and `false`; the
        default is `false`. This option can also be set through the `kn`
        Unicode extension key; if both are provided, this `options`
        property takes precedence.

    [`caseFirst`](#casefirst)

    :   Whether upper case or lower case should sort first. Possible
        values are `"upper"`, `"lower"`, and `"false"` (use the
        locale\'s default); the default is `"false"`. This option can
        also be set through the `kf` Unicode extension key; if both are
        provided, this `options` property takes precedence.

    [`sensitivity`](#sensitivity)

    :   Which differences in the strings should lead to non-zero result
        values. Possible values are:

        [`"base"`](#base)

        :   Only strings that differ in base letters compare as unequal.
            Examples: a ≠ b, a = á, a = A.

        [`"accent"`](#accent)

        :   Only strings that differ in base letters or accents and
            other diacritic marks compare as unequal. Examples: a ≠ b, a
            ≠ á, a = A.

        [`"case"`](#case)

        :   Only strings that differ in base letters or case compare as
            unequal. Examples: a ≠ b, a = á, a ≠ A.

        [`"variant"`](#variant)

        :   Strings that differ in base letters, accents and other
            diacritic marks, or case compare as unequal. Other
            differences may also be taken into consideration. Examples:
            a ≠ b, a ≠ á, a ≠ A.

        The default is `"variant"` for usage `"sort"`; it\'s locale
        dependent for usage `"search"` per spec, but the core
        functionality of `"search"` is accent-insensitive and
        case-insensitive filtering, so `"base"` makes the most sense
        (and perhaps `"case"`).

    [`ignorePunctuation`](#ignorepunctuation)

    :   Whether punctuation should be ignored. Possible values are
        `true` and `false`; the default is `false`.



 
### Exceptions

 

[`RangeError`](../../rangeerror)

:   Thrown if `locales` or `options` contain invalid values.



 
Examples
--------


 
### Using Collator 

 
The following example demonstrates the different potential results for a
string occurring before, after, or at the same level as another:

 
 
[js]


```js
console.log(new Intl.Collator().compare("a", "c")); // -1, or some other negative value
console.log(new Intl.Collator().compare("c", "a")); // 1, or some other positive value
console.log(new Intl.Collator().compare("a", "a")); // 0
```


Note that the results shown in the code above can vary between browsers
and browser versions. This is because the values are
implementation-specific. That is, the specification requires only that
the before and after values are negative and positive.

When usage is `"search"`, the caller should only pay attention to
whether the return value of `compare()` is zero or non-zero. It is
inappropriate to use a `Collator` with usage `"search"` for sorting.



Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-the-intl-collator-constructor]](https://tc39.es/ecma402/#sec-the-intl-collator-constructor)

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

`Collator`

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
available by default. When other locales are specified, the `Collator`
instance silently falls back to `en-US`. To make full ICU (locale) data
available before version 13, see [Node.js documentation on the
`--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

`options_caseFirst_parameter`

24

18

55

15

11

25

56

14

11

1.5

4.4

1.8

0.12.0

`options_collation_parameter`

87

87

85

73

14.1

87

85

No

14.5

14.0

87

1.8

15.0.0

 
See also 
--------

 
-   [`Intl.Collator`](../collator)
-   [`Intl`](../../intl)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator/Collator>

