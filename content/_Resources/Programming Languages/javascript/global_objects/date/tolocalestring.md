Date.prototype.toLocaleString()
===============================

 
The `toLocaleString()` method of [`Date`](../date) instances returns a
string with a language-sensitive representation of this date in the
local timezone. In implementations with [`Intl.DateTimeFormat`
API](../intl/datetimeformat) support, this method simply calls
`Intl.DateTimeFormat`.

Every time `toLocaleString` is called, it has to perform a search in a
big database of localization strings, which is potentially inefficient.
When the method is called many times with the same arguments, it is
better to create a [`Intl.DateTimeFormat`](../intl/datetimeformat)
object and use its [`format()`](../intl/datetimeformat/format) method,
because a `DateTimeFormat` object remembers the arguments passed to it
and may decide to cache a slice of the database, so future `format`
calls can search for localization strings within a more constrained
context.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toLocaleString()
toLocaleString(locales)
toLocaleString(locales, options)
```




 
### Parameters

 
The `locales` and `options` parameters customize the behavior of the
function and let applications specify the language whose formatting
conventions should be used.

In implementations that support the [`Intl.DateTimeFormat`
API](../intl/datetimeformat), these parameters correspond exactly to the
[`Intl.DateTimeFormat()`](../intl/datetimeformat/datetimeformat)
constructor\'s parameters. Implementations without `Intl.DateTimeFormat`
support are asked to ignore both parameters, making the locale used and
the form of the string returned entirely implementation-dependent.

[`locales`](#locales) [Optional]

:   A string with a BCP 47 language tag, or an array of such strings.
    Corresponds to the
    [`locales`](../intl/datetimeformat/datetimeformat#locales) parameter
    of the `Intl.DateTimeFormat()` constructor.

    In implementations without `Intl.DateTimeFormat` support, this
    parameter is ignored and the host\'s locale is usually used.

[`options`](#options) [Optional]

:   An object adjusting the output format. Corresponds to the
    [`options`](../intl/datetimeformat/datetimeformat#options) parameter
    of the `Intl.DateTimeFormat()` constructor. If `weekday`, `year`,
    `month`, `day`, `dayPeriod`, `hour`, `minute`, `second`, and
    `fractionalSecondDigits` are all undefined, then `year`, `month`,
    `day`, `hour`, `minute`, `second` will be set to `"numeric"`.

    In implementations without `Intl.DateTimeFormat` support, this
    parameter is ignored.

See the [`Intl.DateTimeFormat()`
constructor](../intl/datetimeformat/datetimeformat) for details on these
parameters and how to use them.



 
### Return value 

 
A string representing the given date according to language-specific
conventions.

In implementations with `Intl.DateTimeFormat`, this is equivalent to
`new Intl.DateTimeFormat(locales, options).format(date)`.

 
**Note:** Most of the time, the formatting returned by
`toLocaleString()` is consistent. However, the output may vary with
time, language, and implementation --- output variations are by design
and allowed by the specification. You should not compare the results of
`toLocaleString()` to static values.




 
Examples
--------


 
### Using toLocaleString() 

 
Basic use of this method without specifying a `locale` returns a
formatted string in the default locale and with default options.

 
 
[js]


```js
const date = new Date(Date.UTC(2012, 11, 12, 3, 0, 0));

// toLocaleString() without arguments depends on the
// implementation, the default locale, and the default time zone
console.log(date.toLocaleString());
// "12/11/2012, 7:00:00 PM" if run in en-US locale with time zone America/Los_Angeles
```




 
### Checking for support for locales and options parameters 

 
The `locales` and `options` parameters may not be supported in all
implementations, because support for the internationalization API is
optional, and some systems may not have the necessary data. For
implementations without internationalization support, `toLocaleString()`
always uses the system\'s locale, which may not be what you want.
Because any implementation that supports the `locales` and `options`
parameters must support the [`Intl`](../intl) API, you can check the
existence of the latter for support:

 
 
[js]


```js
function toLocaleStringSupportsLocales() {
  return (
    typeof Intl === "object" &&
    !!Intl &&
    typeof Intl.DateTimeFormat === "function"
  );
}
```




 
### Using locales 

 
This example shows some of the variations in localized date and time
formats. In order to get the format of the language used in the user
interface of your application, make sure to specify that language (and
possibly some fallback languages) using the `locales` argument:

 
 
[js]


```js
const date = new Date(Date.UTC(2012, 11, 20, 3, 0, 0));

// Formats below assume the local time zone of the locale;
// America/Los_Angeles for the US

// US English uses month-day-year order and 12-hour time with AM/PM
console.log(date.toLocaleString("en-US"));
// "12/19/2012, 7:00:00 PM"

// British English uses day-month-year order and 24-hour time without AM/PM
console.log(date.toLocaleString("en-GB"));
// "20/12/2012 03:00:00"

// Korean uses year-month-day order and 12-hour time with AM/PM
console.log(date.toLocaleString("ko-KR"));
// "2012. 12. 20. 오후 12:00:00"

// Arabic in most Arabic-speaking countries uses Eastern Arabic numerals
console.log(date.toLocaleString("ar-EG"));
// "٢٠‏/١٢‏/٢٠١٢ ٥:٠٠:٠٠ ص"

// For Japanese, applications may want to use the Japanese calendar,
// where 2012 was the year 24 of the Heisei era
console.log(date.toLocaleString("ja-JP-u-ca-japanese"));
// "24/12/20 12:00:00"

// When requesting a language that may not be supported, such as
// Balinese, include a fallback language (in this case, Indonesian)
console.log(date.toLocaleString(["ban", "id"]));
// "20/12/2012 11.00.00"
```




 
### Using options 

 
The results provided by `toLocaleString()` can be customized using the
`options` parameter:

 
 
[js]


```js
const date = new Date(Date.UTC(2012, 11, 20, 3, 0, 0));

// Request a weekday along with a long date
const options = {
  weekday: "long",
  year: "numeric",
  month: "long",
  day: "numeric",
};
console.log(date.toLocaleString("de-DE", options));
// "Donnerstag, 20. Dezember 2012"

// An application may want to use UTC and make that visible
options.timeZone = "UTC";
options.timeZoneName = "short";
console.log(date.toLocaleString("en-US", options));
// "Thursday, December 20, 2012, GMT"

// Sometimes even the US needs 24-hour time
console.log(date.toLocaleString("en-US", { hour12: false }));
// "12/19/2012, 19:00:00"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.tolocalestring]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.tolocalestring)

  [ECMAScript Internationalization API Specification\
  [\# sup-date.prototype.tolocalestring]](https://tc39.es/ecma402/#sup-date.prototype.tolocalestring)
  -----------------------------------------------------------------------------------------------------------------------------------------


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

`toLocaleString`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`iana_time_zone_names`

24

14

52

15

7

25

56

14

7

1.5

4.4

1.8

0.12.0

`locales`

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

1.0--1.8Only the locale data for `en-US` is available.

13.0.0

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. When other locales are specified, the function
silently falls back to `en-US`. To make full ICU (locale) data available
before version 13, see [Node.js documentation on the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

`options`

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

1.0

0.12.0

 
See also 
--------

 
-   [`Intl.DateTimeFormat`](../intl/datetimeformat)
-   [`Date.prototype.toLocaleDateString()`](tolocaledatestring)
-   [`Date.prototype.toLocaleTimeString()`](tolocaletimestring)
-   [`Date.prototype.toString()`](tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toLocaleString>

