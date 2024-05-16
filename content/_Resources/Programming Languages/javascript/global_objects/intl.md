Intl
====

 
The `Intl` namespace object contains several constructors as well as
functionality common to the internationalization constructors and other
language sensitive functions. Collectively, they comprise the ECMAScript
Internationalization API, which provides language sensitive string
comparison, number formatting, date and time formatting, and more.


 
Description
-----------

 
Unlike most global objects, `Intl` is not a constructor. You cannot use
it with the [`new` operator](../operators/new) or invoke the `Intl`
object as a function. All properties and methods of `Intl` are static
(just like the [`Math`](math) object).

The internationalization constructors as well as several language
sensitive methods of other constructors (listed under [See
also](#see_also)) use a common pattern for identifying locales and
determining the one they will actually use: they all accept `locales`
and `options` arguments, and negotiate the requested locale(s) against
the locales they support using an algorithm specified in the
`options.localeMatcher` property.



 
### locales argument 

 
The `locales` argument is used to determine the locale used in a given
operation. The JavaScript implementation examines `locales`, and then
computes a locale it understands that comes closest to satisfying the
expressed preference. `locales` may be:

-   `undefined` (or omitted): The implementation\'s default locale will
    be used.
-   A locale: A locale identifier or an [`Intl.Locale`](intl/locale)
    object that wraps a locale identifier.
-   A list of locales: Any other value, that will be converted into an
    object and then treated as an array of locales.

In the latter two cases, the actual locale used is the best-supported
locale determined by [locale
negotiation](#locale_identification_and_negotiation). If a locale
identifier is not a string or an object, a [`TypeError`](typeerror) is
thrown. If a locale identifier is a string that\'s syntactically
invalid, a [`RangeError`](rangeerror) is thrown. If a locale identifier
is well-formed but the implementation doesn\'t recognize it, it is
ignored and the next locale in the list is considered, eventually
falling back to the system\'s locale. However, you shouldn\'t rely on a
particular locale name being ignored, because the implementation may add
data for any locale in the future. For example,
`new Intl.DateTimeFormat("default")` uses the implementation\'s default
locale only because `"default"` is syntactically valid but not
recognized as any locale.

A locale identifier is a string that consists of:

1.  A language subtag with 2--3 or 5--8 letters
2.  A script subtag with 4 letters [Optional]
3.  A region subtag with either 2 letters or 3 digits [Optional]
4.  One or more variant subtags (all of which must be unique), each with
    either 5--8 alphanumerals or a digit followed by 3 alphanumerals
    [Optional]
5.  One or more BCP 47 extension sequences [Optional]
6.  A private-use extension sequence [Optional]

Each subtag and sequence are separated by hyphens. Locale identifiers
are case-insensitive
[ASCII](https://developer.mozilla.org/en-US/docs/Glossary/ASCII).
However, it\'s conventional to use title case (the first letter is
capitalized, successive letters are lower case) for script subtags,
upper case for region subtags, and lower case for everything else. For
example:

-   `"hi"`: Hindi (language)
-   `"de-AT"`: German (language) as used in Austria (region)
-   `"zh-Hans-CN"`: Chinese (language) written in simplified characters
    (script) as used in China (region)
-   `"en-emodeng"`: English (language) in the \"Early modern English\"
    dialect (variant)

Subtags identifying languages, scripts, regions (including countries),
and (rarely used) variants are registered in the [IANA Language Subtag
Registry](https://www.iana.org/assignments/language-subtag-registry/language-subtag-registry).
This registry is periodically updated over time, and implementations may
not always be up to date, so don\'t rely too much on subtags being
universally supported.

BCP 47 extension sequences consist of a single digit or letter (other
than `"x"`) and one or more two- to eight-letter or digit subtags
separated by hyphens. Only one sequence is permitted for each digit or
letter: `"de-a-foo-a-foo"` is invalid. BCP 47 extension subtags are
defined in the [Unicode CLDR
Project](https://github.com/unicode-org/cldr/tree/main/common/bcp47).
Currently only two extensions have defined semantics:

-   The `"u"` (Unicode) extension can be used to request additional
    customization of `Intl` API objects. Examples:
    -   `"de-DE-u-co-phonebk"`: Use the phonebook variant of the German
        sort order, which interprets umlauted vowels as corresponding
        character pairs: ä → ae, ö → oe, ü → ue.
    -   `"th-TH-u-nu-thai"`: Use Thai digits (๐, ๑, ๒, ๓, ๔, ๕, ๖, ๗, ๘,
        ๙) in number formatting.
    -   `"ja-JP-u-ca-japanese"`: Use the Japanese calendar in date and
        time formatting, so that 2013 is expressed as the year 25 of the
        Heisei period, or 平成 25.
    -   `"en-GB-u-ca-islamic"`: use British English with the Islamic
        (Hijri) calendar, where the Gregorian date 14 October, 2017 is
        the Hijri date 24 Muharram, 1439.
-   The `"t"` (transformed) extension indicates transformed content: for
    example, text that was translated from another locale. No `Intl`
    functionality currently considers the `"t"` extension. However, this
    extension sometimes contains a nested locale (with no extensions):
    for example, the transformed extension in `"de-t-en"` contains the
    locale identifier for English. If a nested locale is present, it
    must be a valid locale identifier. For example, because
    `"en-emodeng-emodeng"` is invalid (because it contains a duplicate
    `emodeng` variant subtag), `"de-t-en-emodeng-emodeng"` is also
    invalid.

Finally, a private-use extension sequence using the letter `"x"` may
appear, followed by one or more one- to eight-letter or digit subtags
separated by hyphens. This allows applications to encode information for
their own private use, that will be ignored by all `Intl` operations.



 
### options argument 

 
The `options` argument must be an object with properties that vary
between constructors and functions. If the `options` argument is not
provided or is undefined, default values are used for all properties.

One property is supported by all language sensitive constructors and
functions: The `localeMatcher` property, whose value must be a string
`"lookup"` or `"best fit"` and which selects one of the locale matching
algorithms described below.



 
### Locale identification and negotiation 

 
The list of locales specified by the `locales` argument, after Unicode
extensions have been removed from them, is interpreted as a prioritized
request from the application. The runtime compares it against the
locales it has available and picks the best one available. Two matching
algorithms exist: the `"lookup"` matcher follows the Lookup algorithm
specified in [BCP
47](https://datatracker.ietf.org/doc/html/rfc4647#section-3.4); the
`"best fit"` matcher lets the runtime provide a locale that\'s at least,
but possibly more, suited for the request than the result of the Lookup
algorithm. If the application doesn\'t provide a `locales` argument, or
the runtime doesn\'t have a locale that matches the request, then the
runtime\'s default locale is used. The matcher can be selected using a
property of the `options` argument (see below).

If the selected locale identifier had a Unicode extension sequence, that
extension is now used to customize the constructed object or the
behavior of the function. Each constructor or function supports only a
subset of the keys defined for the Unicode extension, and the supported
values often depend on the locale identifier. For example, the `"co"`
key (collation) is only supported by [`Intl.Collator`](intl/collator),
and its `"phonebk"` value is only supported for German.



 
Static properties 
-----------------

 

[`Intl.Collator`](intl/collator)

:   Constructor for collators, which are objects that enable
    language-sensitive string comparison.

[`Intl.DateTimeFormat`](intl/datetimeformat)

:   Constructor for objects that enable language-sensitive date and time
    formatting.

[`Intl.DisplayNames`](intl/displaynames)

:   Constructor for objects that enable the consistent translation of
    language, region and script display names.

[`Intl.DurationFormat`](intl/durationformat) [Experimental]

:   Constructor for objects that enable locale-sensitive duration
    formatting.

[`Intl.ListFormat`](intl/listformat)

:   Constructor for objects that enable language-sensitive list
    formatting.

[`Intl.Locale`](intl/locale)

:   Constructor for objects that represents a Unicode locale identifier.

[`Intl.NumberFormat`](intl/numberformat)

:   Constructor for objects that enable language-sensitive number
    formatting.

[`Intl.PluralRules`](intl/pluralrules)

:   Constructor for objects that enable plural-sensitive formatting and
    language-specific rules for plurals.

[`Intl.RelativeTimeFormat`](intl/relativetimeformat)

:   Constructor for objects that enable language-sensitive relative time
    formatting.

[`Intl.Segmenter`](intl/segmenter)

:   Constructor for objects that enable locale-sensitive text
    segmentation.

[`Intl[@@toStringTag]`](#intltostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"Intl"`. This property is used in
    [`Object.prototype.toString()`](object/tostring).



 
Static methods 
--------------

 

[`Intl.getCanonicalLocales()`](intl/getcanonicallocales)

:   Returns canonical locale names.

[`Intl.supportedValuesOf()`](intl/supportedvaluesof)

:   Returns a sorted array containing the supported unique calendar,
    collation, currency, numbering systems, or unit values supported by
    the implementation.



 
Examples
--------


 
### Formatting dates and numbers 

 
You can use `Intl` to format dates and numbers in a form that\'s
conventional for a specific language and region:

 
 
[js]


```js
const count = 26254.39;
const date = new Date("2012-05-24");

function log(locale) {
  console.log(
    `${new Intl.DateTimeFormat(locale).format(date)}${new Intl.NumberFormat(
      locale,
    ).format(count)}`,
  );
}

log("en-US"); // 5/24/2012 26,254.39

log("de-DE"); // 24.5.2012 26.254,39
```




 
### Using the browser\'s preferred language 

 
Instead of passing a hardcoded locale name to the `Intl` methods, you
can use the user\'s preferred language provided by
[`navigator.language`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/language):

 
 
[js]


```js
const date = new Date("2012-05-24");

const formattedDate = new Intl.DateTimeFormat(navigator.language).format(date);
```


Alternatively, the
[`navigator.languages`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/languages)
property provides a sorted list of the user\'s preferred languages. This
list can be passed directly to the `Intl` constructors to implement
preference-based fallback selection of locales. The [locale
negotiation](#locale_identification_and_negotiation) process is used to
pick the most appropriate locale available:

 
 
[js]


```js
const count = 26254.39;

const formattedCount = new Intl.NumberFormat(navigator.languages).format(count);
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\# intl-object]](https://tc39.es/ecma402/#intl-object)

  -----------------------------------------------------------------------


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

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `Collator()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator/Collator)
for more details.

`DateTimeFormat`

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
available by default. See [the `DateTimeFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/DateTimeFormat)
for more details.

`DisplayNames`

81

81

86

68

14.1

81

86

58

14.5

13.0

81

1.8

14.0.0

`DurationFormat`

No

No

No

No

16.4

No

No

No

16.4

No

No

No

No

`ListFormat`

72

79

78

60

14.1Only available on macOS Big Sur (11) and above.

72

79

51

14.5

11.0

72

1.8

12.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `ListFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/ListFormat)
for more details.

`Locale`

74

79

75

62

14

74

79

53

14

11.0

74

1.8

12.0.0

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

`RelativeTimeFormat`

71

79

65

58

14

71

65

50

14

10.0

71

1.8

12.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `RelativeTimeFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/RelativeTimeFormat/RelativeTimeFormat)
for more details.

`Segmenter`

87

87

preview

73

14.1

87

No

62

14.5

14.0

87

1.8

16.0.0

`Segments`

87

87

No

73

14.1

87

No

62

14.5

14.0

87

1.8

16.0.0

`Intl`

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

`getCanonicalLocales`

54

16

48

41

10.1

54

56

41

10.3

6.0

54

1.8

7.0.0

`supportedValuesOf`

99

99

93

85

15.4

99

93

68

15.4

18.0

99

1.19

18.0.0

 
See also 
--------

 
-   [`String.prototype.localeCompare()`](string/localecompare)
-   [`Number.prototype.toLocaleString()`](number/tolocalestring)
-   [`Date.prototype.toLocaleString()`](date/tolocalestring)
-   [`Date.prototype.toLocaleDateString()`](date/tolocaledatestring)
-   [`Date.prototype.toLocaleTimeString()`](date/tolocaletimestring)
-   [`navigator.language`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/language)
-   [`navigator.languages`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/languages)
-   [The ECMAScript Internationalization
    API](https://norbertlindenberg.com/2012/12/ecmascript-internationalization-api/index.html)
    by Norbert Lindenberg (2012)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl>

