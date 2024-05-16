Intl.Locale
===========

 
The `Intl.Locale` object is a standard built-in property of the Intl
object that represents a Unicode locale identifier.


 
Try it 
------

 



 
Description
-----------

 
The `Intl.Locale` object was created to allow for easier manipulation of
Unicode locales. Unicode represents locales with a string, called a
*locale identifier*. The locale identifier consists of a *language
identifier* and *extension tags*. Language identifiers are the core of
the locale, consisting of *language*, *script*, and *region subtags*.
Additional information about the locale is stored in the optional
*extension tags*. Extension tags hold information about locale aspects
such as calendar type, clock type, and numbering system type.

Traditionally, the Intl API used strings to represent locales, just as
Unicode does. This is a simple and lightweight solution that works well.
Adding a Locale class, however, adds ease of parsing and manipulating
the language, script, and region, as well as extension tags. The
following properties of `Intl.Locale` correspond to Unicode locale
identifier subtags:

 
  Property                                      Corresponding subtag
  --------------------------------------------- ------------------------------
  [`language`](locale/language)                 `language` (first part)
  [`script`](locale/script)                     `script` (second part)
  [`region`](locale/region)                     `region` (second/third part)
  [`calendar`](locale/calendar)                 `ca` (extension)
  [`caseFirst`](locale/casefirst)               `kf` (extension)
  [`collation`](locale/collation)               `co` (extension)
  [`hourCycle`](locale/hourcycle)               `hc` (extension)
  [`numberingSystem`](locale/numberingsystem)   `nu` (extension)
  [`numeric`](locale/numeric)                   `kn` (extension)


The information above is exactly provided as-is when the `Locale` object
is constructed, without consulting any external database. The
`Intl.Locale` object additionally provides some methods that return
information about the locale\'s real-world information, such as
available calendars, collations, and numbering systems.



 
Constructor
-----------

 

[`Intl.Locale()`](locale/locale)

:   Creates a new `Locale` object.



 
Instance properties 
-------------------

 
These properties are defined on `Intl.Locale.prototype` and shared by
all `Intl.Locale` instances.

[`Intl.Locale.prototype.baseName`](locale/basename)

:   Returns basic, core information about the `Locale` in the form of a
    substring of the complete data string.

[`Intl.Locale.prototype.calendar`](locale/calendar)

:   Returns the part of the `Locale` that indicates the Locale\'s
    calendar era.

[`Intl.Locale.prototype.caseFirst`](locale/casefirst)

:   Returns whether case is taken into account for the locale\'s
    collation rules.

[`Intl.Locale.prototype.collation`](locale/collation)

:   Returns the collation type for the `Locale`, which is used to order
    strings according to the locale\'s rules.

[`Intl.Locale.prototype.constructor`](../object/constructor)

:   The constructor function that created the instance object. For
    `Intl.Locale` instances, the initial value is the
    [`Intl.Locale`](locale/locale) constructor.

[`Intl.Locale.prototype.hourCycle`](locale/hourcycle)

:   Returns the time keeping format convention used by the locale.

[`Intl.Locale.prototype.language`](locale/language)

:   Returns the language associated with the locale.

[`Intl.Locale.prototype.numberingSystem`](locale/numberingsystem)

:   Returns the numeral system used by the locale.

[`Intl.Locale.prototype.numeric`](locale/numeric)

:   Returns whether the locale has special collation handling for
    numeric characters.

[`Intl.Locale.prototype.region`](locale/region)

:   Returns the region of the world (usually a country) associated with
    the locale.

[`Intl.Locale.prototype.script`](locale/script)

:   Returns the script used for writing the particular language used in
    the locale.

[`Intl.Locale.prototype[@@toStringTag]`](#intl.locale.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](../symbol/tostringtag)
    property is the string `"Intl.Locale"`. This property is used in
    [`Object.prototype.toString()`](../object/tostring).



 
Instance methods 
----------------

 

[`Intl.Locale.prototype.getCalendars()`](locale/getcalendars)

:   Returns an [`Array`](../array) of available calendar identifiers,
    according to the locale\'s rules.

[`Intl.Locale.prototype.getCollations()`](locale/getcollations)

:   Returns an [`Array`](../array) of the collation types for the
    `Locale`.

[`Intl.Locale.prototype.getHourCycles()`](locale/gethourcycles)

:   Returns an [`Array`](../array) of hour cycle identifiers, indicating
    either the 12-hour clock (\"h12\"), the Japanese 12-hour clock
    (\"h11\"), the 24-hour clock (\"h23\"), or the unused format
    \"h24\".

[`Intl.Locale.prototype.getNumberingSystems()`](locale/getnumberingsystems)

:   Returns an [`Array`](../array) of numbering system identifiers
    available according to the locale\'s rules.

[`Intl.Locale.prototype.getTextInfo()`](locale/gettextinfo)

:   Returns the part indicating the ordering of characters `ltr`
    (left-to-right) or `rtl` (right-to-left).

[`Intl.Locale.prototype.getTimeZones()`](locale/gettimezones)

:   Returns an [`Array`](../array) of time zone identifiers, associated
    with the `Locale`.

[`Intl.Locale.prototype.getWeekInfo()`](locale/getweekinfo)

:   Returns [UTS 35\'s Week
    Elements](https://www.unicode.org/reports/tr35/tr35-dates.html#Date_Patterns_Week_Elements)
    according to the locale rules.

[`Intl.Locale.prototype.maximize()`](locale/maximize)

:   Gets the most likely values for the language, script, and region of
    the locale based on existing values.

[`Intl.Locale.prototype.minimize()`](locale/minimize)

:   Attempts to remove information about the locale that would be added
    by calling [`maximize()`](locale/maximize).

[`Intl.Locale.prototype.toString()`](locale/tostring)

:   Returns the Locale\'s full locale identifier string.



 
Examples
--------


 
### Basic usage 

 
At its very simplest, the [`Intl.Locale()`](locale/locale) constructor
takes a locale identifier string as its argument:

 
 
[js]


```js
const us = new Intl.Locale("en-US");
```




 
### Using the Locale constructor with an options object 

 
The constructor also takes an optional configuration object argument,
which can contain any of several extension types. For example, set the
[`hourCycle`](locale/hourcycle) property of the configuration object to
your desired hour cycle type, and then pass it into the constructor:

 
 
[js]


```js
const us12hour = new Intl.Locale("en-US", { hourCycle: "h12" });
console.log(us12hour.hourCycle); // Prints "h12"
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\# locale-objects]](https://tc39.es/ecma402/#locale-objects)

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

`baseName`

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

`calendar`

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

`caseFirst`

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

`collation`

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

`getCalendars`

99Implemented as an accessor property.

99Implemented as an accessor property.

No

85Implemented as an accessor property.

17

15.4--previewImplemented as an accessor property.

99Implemented as an accessor property.

No

68Implemented as an accessor property.

17

15.4Implemented as an accessor property.

18.0Implemented as an accessor property.

99Implemented as an accessor property.

1.19

18.0.0Implemented as an accessor property.

`getCollations`

99Implemented as an accessor property.

99Implemented as an accessor property.

No

85Implemented as an accessor property.

17

15.4--previewImplemented as an accessor property.

99Implemented as an accessor property.

No

68Implemented as an accessor property.

17

15.4Implemented as an accessor property.

18.0Implemented as an accessor property.

99Implemented as an accessor property.

1.19

18.0.0Implemented as an accessor property.

`getHourCycles`

99Implemented as an accessor property.

99Implemented as an accessor property.

No

85Implemented as an accessor property.

17

15.4--previewImplemented as an accessor property.

99Implemented as an accessor property.

No

68Implemented as an accessor property.

17

15.4Implemented as an accessor property.

18.0Implemented as an accessor property.

99Implemented as an accessor property.

1.19

18.0.0Implemented as an accessor property.

`getNumberingSystems`

99Implemented as an accessor property.

99Implemented as an accessor property.

No

85Implemented as an accessor property.

17

15.4--previewImplemented as an accessor property.

99Implemented as an accessor property.

No

68Implemented as an accessor property.

17

15.4Implemented as an accessor property.

18.0Implemented as an accessor property.

99Implemented as an accessor property.

1.19

18.0.0Implemented as an accessor property.

`getTextInfo`

99Implemented as an accessor property.

99Implemented as an accessor property.

No

85Implemented as an accessor property.

17

15.4--previewImplemented as an accessor property.

99Implemented as an accessor property.

No

68Implemented as an accessor property.

17

15.4Implemented as an accessor property.

18.0Implemented as an accessor property.

99Implemented as an accessor property.

1.19

18.0.0Implemented as an accessor property.

`getTimeZones`

99Implemented as an accessor property.

99Implemented as an accessor property.

No

85Implemented as an accessor property.

17

15.4--previewImplemented as an accessor property.

99Implemented as an accessor property.

No

68Implemented as an accessor property.

17

15.4Implemented as an accessor property.

18.0Implemented as an accessor property.

99Implemented as an accessor property.

1.19

18.0.0Implemented as an accessor property.

`getWeekInfo`

99Implemented as an accessor property.

99Implemented as an accessor property.

No

85Implemented as an accessor property.

17

15.4--previewImplemented as an accessor property.

99Implemented as an accessor property.

No

68Implemented as an accessor property.

17

15.4Implemented as an accessor property.

18.0Implemented as an accessor property.

99Implemented as an accessor property.

1.19

18.0.0Implemented as an accessor property.

`hourCycle`

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

`language`

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

`maximize`

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

`minimize`

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

`numberingSystem`

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

`numeric`

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

`region`

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

`script`

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

`toString`

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

 
See also 
--------

 
-   [Polyfill of `Intl.Locale` in
    FormatJS](https://formatjs.io/docs/polyfills/intl-locale/)
-   [`Intl`](../intl)
-   [Canonical Unicode Locale
    Identifiers](https://www.unicode.org/reports/tr35/#Canonical_Unicode_Locale_Identifiers)
    in the Unicode locale data markup language spec



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale>

