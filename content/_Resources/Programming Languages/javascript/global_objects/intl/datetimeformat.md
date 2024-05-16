Intl.DateTimeFormat
===================

 
The `Intl.DateTimeFormat` object enables language-sensitive date and
time formatting.


 
Try it 
------

 



 
Constructor
-----------

 

[`Intl.DateTimeFormat()`](datetimeformat/datetimeformat)

:   Creates a new `Intl.DateTimeFormat` object.



 
Static methods 
--------------

 

[`Intl.DateTimeFormat.supportedLocalesOf()`](datetimeformat/supportedlocalesof)

:   Returns an array containing those of the provided locales that are
    supported without having to fall back to the runtime\'s default
    locale.



 
Instance properties 
-------------------

 
These properties are defined on `Intl.DateTimeFormat.prototype` and
shared by all `Intl.DateTimeFormat` instances.

[`Intl.DateTimeFormat.prototype.constructor`](../object/constructor)

:   The constructor function that created the instance object. For
    `Intl.DateTimeFormat` instances, the initial value is the
    [`Intl.DateTimeFormat`](datetimeformat/datetimeformat) constructor.

[`Intl.DateTimeFormat.prototype[@@toStringTag]`](#intl.datetimeformat.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](../symbol/tostringtag)
    property is the string `"Intl.DateTimeFormat"`. This property is
    used in [`Object.prototype.toString()`](../object/tostring).



 
Instance methods 
----------------

 

[`Intl.DateTimeFormat.prototype.format()`](datetimeformat/format)

:   Getter function that formats a date according to the locale and
    formatting options of this `DateTimeFormat` object.

[`Intl.DateTimeFormat.prototype.formatRange()`](datetimeformat/formatrange)

:   This method receives two [Dates](../date) and formats the date range
    in the most concise way based on the locale and options provided
    when instantiating `DateTimeFormat`.

[`Intl.DateTimeFormat.prototype.formatRangeToParts()`](datetimeformat/formatrangetoparts)

:   This method receives two [Dates](../date) and returns an Array of
    objects containing the locale-specific tokens representing each part
    of the formatted date range.

[`Intl.DateTimeFormat.prototype.formatToParts()`](datetimeformat/formattoparts)

:   Returns an [`Array`](../array) of objects representing the date
    string in parts that can be used for custom locale-aware formatting.

[`Intl.DateTimeFormat.prototype.resolvedOptions()`](datetimeformat/resolvedoptions)

:   Returns a new object with properties reflecting the locale and
    formatting options computed during initialization of the object.



 
Examples
--------


 
### Using DateTimeFormat 

 
In basic use without specifying a locale, `DateTimeFormat` uses the
default locale and default options.

 
 
[js]


```js
const date = new Date(Date.UTC(2012, 11, 20, 3, 0, 0));

// toLocaleString without arguments depends on the implementation,
// the default locale, and the default time zone
console.log(new Intl.DateTimeFormat().format(date));
// "12/19/2012" if run with en-US locale (language) and time zone America/Los_Angeles (UTC-0800)
```




 
### Using locales 

 
This example shows some of the variations in localized date and time
formats. In order to get the format of the language used in the user
interface of your application, make sure to specify that language (and
possibly some fallback languages) using the `locales` argument:

 
 
[js]


```js
const date = new Date(Date.UTC(2012, 11, 20, 3, 0, 0));

// Results below use the time zone of America/Los_Angeles (UTC-0800, Pacific Standard Time)

// US English uses month-day-year order
console.log(new Intl.DateTimeFormat("en-US").format(date));
// "12/19/2012"

// British English uses day-month-year order
console.log(new Intl.DateTimeFormat("en-GB").format(date));
// "19/12/2012"

// Korean uses year-month-day order
console.log(new Intl.DateTimeFormat("ko-KR").format(date));
// "2012. 12. 19."

// Arabic in most Arabic speaking countries uses real Arabic digits
console.log(new Intl.DateTimeFormat("ar-EG").format(date));
// "١٩‏/١٢‏/٢٠١٢"

// for Japanese, applications may want to use the Japanese calendar,
// where 2012 was the year 24 of the Heisei era
console.log(new Intl.DateTimeFormat("ja-JP-u-ca-japanese").format(date));
// "24/12/19"

// when requesting a language that may not be supported, such as
// Balinese, include a fallback language, in this case Indonesian
console.log(new Intl.DateTimeFormat(["ban", "id"]).format(date));
// "19/12/2012"
```




 
### Using options 

 
The date and time formats can be customized using the `options`
argument:

 
 
[js]


```js
const date = new Date(Date.UTC(2012, 11, 20, 3, 0, 0, 200));

// request a weekday along with a long date
let options = {
  weekday: "long",
  year: "numeric",
  month: "long",
  day: "numeric",
};
console.log(new Intl.DateTimeFormat("de-DE", options).format(date));
// "Donnerstag, 20. Dezember 2012"

// an application may want to use UTC and make that visible
options.timeZone = "UTC";
options.timeZoneName = "short";
console.log(new Intl.DateTimeFormat("en-US", options).format(date));
// "Thursday, December 20, 2012, GMT"

// sometimes you want to be more precise
options = {
  hour: "numeric",
  minute: "numeric",
  second: "numeric",
  timeZone: "Australia/Sydney",
  timeZoneName: "short",
};
console.log(new Intl.DateTimeFormat("en-AU", options).format(date));
// "2:00:00 pm AEDT"

// sometimes you want to be very precise
options.fractionalSecondDigits = 3; //number digits for fraction-of-seconds
console.log(new Intl.DateTimeFormat("en-AU", options).format(date));
// "2:00:00.200 pm AEDT"

// sometimes even the US needs 24-hour time
options = {
  year: "numeric",
  month: "numeric",
  day: "numeric",
  hour: "numeric",
  minute: "numeric",
  second: "numeric",
  hour12: false,
  timeZone: "America/Los_Angeles",
};
console.log(new Intl.DateTimeFormat("en-US", options).format(date));
// "12/19/2012, 19:00:00"

// to specify options but use the browser's default locale, use undefined
console.log(new Intl.DateTimeFormat(undefined, options).format(date));
// "12/19/2012, 19:00:00"

// sometimes it's helpful to include the period of the day
options = { hour: "numeric", dayPeriod: "short" };
console.log(new Intl.DateTimeFormat("en-US", options).format(date));
// 10 at night
```


The used calendar and numbering formats can also be set independently
via `options` arguments:

 
 
[js]


```js
const options = { calendar: "chinese", numberingSystem: "arab" };
const dateFormat = new Intl.DateTimeFormat(undefined, options);
const usedOptions = dateFormat.resolvedOptions();

console.log(usedOptions.calendar);
// "chinese"

console.log(usedOptions.numberingSystem);
// "arab"

console.log(usedOptions.timeZone);
// "America/New_York" (the users default timezone)
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  datetimeformat-objects]](https://tc39.es/ecma402/#datetimeformat-objects)

  -----------------------------------------------------------------------------------


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

13.0.0

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. When other locales are specified, the
`DateTimeFormat` instance silently falls back to `en-US`. To make full
ICU (locale) data available before version 13, see [Node.js
documentation on the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

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

`format`

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

`formatRange`

76

79

91

63

14.1

76

91

54

14.5

12.0

76

1.8

12.9.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `DateTimeFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/DateTimeFormat)
for more details.

`formatRangeToParts`

76

79

91

63

14.1

76

91

54

14.5

12.0

76

1.8

12.9.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `DateTimeFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/DateTimeFormat)
for more details.

`formatToParts`

57Before version 71, `formatToParts()` returned an object with an
incorrectly cased type key of `dayperiod`. Version 71 and later use the
specification defined `dayPeriod`. See [bug
865351](https://crbug.com/865351).

18

51

44Before version 58, `formatToParts()` returned an object with an
incorrectly cased type key of `dayperiod`. Version 58 and later use the
specification defined `dayPeriod`. See [bug
865351](https://crbug.com/865351).

11

57Before version 71, `formatToParts()` returned an object with an
incorrectly cased type key of `dayperiod`. Version 71 and later use the
specification defined `dayPeriod`. See [bug
865351](https://crbug.com/865351).

56

43Before version 50, `formatToParts()` returned an object with an
incorrectly cased type key of `dayperiod`. Version 50 and later use the
specification defined `dayPeriod`. See [bug
865351](https://crbug.com/865351).

11

7.0Before version 71, `formatToParts()` returned an object with an
incorrectly cased type key of `dayperiod`. Version 71 and later use the
specification defined `dayPeriod`. See [bug
865351](https://crbug.com/865351).

57Before version 71, `formatToParts()` returned an object with an
incorrectly cased type key of `dayperiod`. Version 71 and later use the
specification defined `dayPeriod`. See [bug
865351](https://crbug.com/865351).

1.8

8.0.0\[\"Before version 12.0.0, `formatToParts()` returned an object
with an incorrectly cased type key of `dayperiod`. Version 12.0.0 and
later use the specification defined `dayPeriod`. See [bug
865351](https://crbug.com/865351).\", \"Before version 13.0.0, only the
locale data for `en-US` is available by default. See [the
`DateTimeFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/DateTimeFormat)
for more details.\"\]

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
available by default. See [the `DateTimeFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/DateTimeFormat)
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

 
-   [Polyfill of `Intl.DateTimeFormat` in
    FormatJS](https://formatjs.io/docs/polyfills/intl-datetimeformat/)
-   [`Intl`](../intl)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat>

