Date
====

 
JavaScript `Date` objects represent a single moment in time in a
platform-independent format. `Date` objects encapsulate an integral
number that represents milliseconds since the midnight at the beginning
of January 1, 1970, UTC (the *epoch*).

 
**Note:** TC39 is working on
[Temporal](https://tc39.es/proposal-temporal/docs/index.html), a new
Date/Time API. Read more about it on the [Igalia
blog](https://blogs.igalia.com/compilers/2020/06/23/dates-and-times-in-javascript/).
It is not yet ready for production use!



 
Description
-----------


 
### The epoch, timestamps, and invalid date 

 
A JavaScript date is fundamentally specified as the time in milliseconds
that has elapsed since the
[epoch](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-time-values-and-time-range),
which is defined as the midnight at the beginning of January 1, 1970,
UTC (equivalent to the [UNIX
epoch](https://developer.mozilla.org/en-US/docs/Glossary/Unix_time)).
This timestamp is *timezone-agnostic* and uniquely defines an instant in
history.

 
**Note:** While the time value at the heart of a Date object is UTC, the
basic methods to fetch the date and time or its components all work in
the local (i.e. host system) time zone and offset.


The maximum timestamp representable by a `Date` object is slightly
smaller than the maximum safe integer
([`Number.MAX_SAFE_INTEGER`](number/max_safe_integer), which is
9,007,199,254,740,991). A `Date` object can represent a maximum of
±8,640,000,000,000,000 milliseconds, or ±100,000,000 (one hundred
million) days, relative to the epoch. This is the range from April 20,
271821 BC to September 13, 275760 AD. Any attempt to represent a time
outside this range results in the `Date` object holding a timestamp
value of [`NaN`](nan), which is an \"Invalid Date\".

 
 
[js]


```js
console.log(new Date(8.64e15).toString()); // "Sat Sep 13 275760 00:00:00 GMT+0000 (Coordinated Universal Time)"
console.log(new Date(8.64e15 + 1).toString()); // "Invalid Date"
```


There are various methods that allow you to interact with the timestamp
stored in the date:

-   You can interact with the timestamp value directly using the
    [`getTime()`](date/gettime) and [`setTime()`](date/settime) methods.
-   The [`valueOf()`](date/valueof) and
    [`[@@toPrimitive]()`](date/@@toprimitive) (when passed `"number"`)
    methods --- which are automatically called in [number
    coercion](number#number_coercion) --- return the timestamp, causing
    `Date` objects to behave like their timestamps when used in number
    contexts.
-   All static methods ([`Date.now()`](date/now),
    [`Date.parse()`](date/parse), and [`Date.UTC()`](date/utc)) return
    timestamps instead of `Date` objects.
-   The [`Date()`](date/date) constructor can be called with a timestamp
    as the only argument.



 
### Date components and time zones 

 
A date is represented internally as a single number, the *timestamp*.
When interacting with it, the timestamp needs to be interpreted as a
structured date-and-time representation. There are always two ways to
interpret a timestamp: as a local time or as a Coordinated Universal
Time (UTC), the global standard time defined by the World Time Standard.
The local timezone is not stored in the date object, but is determined
by the host environment (user\'s device).

 
**Note:** UTC should not be confused with the [Greenwich Mean
Time](https://en.wikipedia.org/wiki/Greenwich_Mean_Time) (GMT), because
they are not always equal --- this is explained in more detail in the
linked Wikipedia page.


For example, the timestamp 0 represents a unique instant in history, but
it can be interpreted in two ways:

-   As a UTC time, it is midnight at the beginning of January 1, 1970,
    UTC,
-   As a local time in New York (UTC-5), it is 19:00:00 on December
    31, 1969.

The [`getTimezoneOffset()`](date/gettimezoneoffset) method returns the
difference between UTC and the local time in minutes. Note that the
timezone offset does not only depend on the current timezone, but also
on the time represented by the `Date` object, because of daylight saving
time and historical changes. In essence, the timezone offset is the
offset from UTC time, at the time represented by the `Date` object and
at the location of the host environment.

There are two groups of `Date` methods: one group gets and sets various
date components by interpreting the timestamp as a local time, while the
other uses UTC.

 
Component




Local

UTC

Get

Set

Get

Set

Year

[`getFullYear()`](date/getfullyear)

[`setFullYear()`](date/setfullyear)

[`getUTCFullYear()`](date/getutcfullyear)

[`setUTCFullYear()`](date/setutcfullyear)

Month

[`getMonth()`](date/getmonth)

[`setMonth()`](date/setmonth)

[`getUTCMonth()`](date/getutcmonth)

[`setUTCMonth()`](date/setutcmonth)

Date (of month)

[`getDate()`](date/getdate)

[`setDate()`](date/setdate)

[`getUTCDate()`](date/getutcdate)

[`setUTCDate()`](date/setutcdate)

Hours

[`getHours()`](date/gethours)

[`setHours()`](date/sethours)

[`getUTCHours()`](date/getutchours)

[`setUTCHours()`](date/setutchours)

Minutes

[`getMinutes()`](date/getminutes)

[`setMinutes()`](date/setminutes)

[`getUTCMinutes()`](date/getutcminutes)

[`setUTCMinutes()`](date/setutcminutes)

Seconds

[`getSeconds()`](date/getseconds)

[`setSeconds()`](date/setseconds)

[`getUTCSeconds()`](date/getutcseconds)

[`setUTCSeconds()`](date/setutcseconds)

Milliseconds

[`getMilliseconds()`](date/getmilliseconds)

[`setMilliseconds()`](date/setmilliseconds)

[`getUTCMilliseconds()`](date/getutcmilliseconds)

[`setUTCMilliseconds()`](date/setutcmilliseconds)

Day (of week)

[`getDay()`](date/getday)

N/A

[`getUTCDay()`](date/getutcday)

N/A

The [`Date()`](date/date) constructor can be called with two or more
arguments, in which case they are interpreted as the year, month, day,
hour, minute, second, and millisecond, respectively, in local time.
[`Date.UTC()`](date/utc) works similarly, but it interprets the
components as UTC time and also accepts a single argument representing
the year.

 
**Note:** Some methods, including the `Date()` constructor,
`Date.UTC()`, and the deprecated
[`getYear()`](date/getyear)/[`setYear()`](date/setyear) methods,
interpret a two-digit year as a year in the 1900s. For example,
`new Date(99, 5, 24)` is interpreted as June 24, 1999, not June 24, 99.
See [Interpretation of two-digit
years](#interpretation_of_two-digit_years) for more information.


When a segment overflows or underflows its expected range, it usually
\"carries over to\" or \"borrows from\" the higher segment. For example,
if the month is set to 12 (months are zero-based, so December is 11), it
become the January of the next year. If the day of month is set to 0, it
becomes the last day of the previous month. This also applies to dates
specified with the [date time string format](#date_time_string_format).

 
### Date time string format 

 
There are many ways to format a date as a string. The JavaScript
specification only specifies one format to be universally supported: the
[*date time string
format*](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date-time-string-format),
a simplification of the ISO 8601 calendar date extended format. The
format is as follows:

```text
YYYY-MM-DDTHH:mm:ss.sssZ
```

-   `YYYY` is the year, with four digits (`0000` to `9999`), or as an
    *expanded year* of `+` or `-` followed by six digits. The sign is
    required for expanded years. `-000000` is explicitly disallowed as a
    valid year.
-   `MM` is the month, with two digits (`01` to `12`). Defaults to `01`.
-   `DD` is the day of the month, with two digits (`01` to `31`).
    Defaults to `01`.
-   `T` is a literal character, which indicates the beginning of the
    *time* part of the string. The `T` is required when specifying the
    time part.
-   `HH` is the hour, with two digits (`00` to `23`). As a special case,
    `24:00:00` is allowed, and is interpreted as midnight at the
    beginning of the next day. Defaults to `00`.
-   `mm` is the minute, with two digits (`00` to `59`). Defaults to
    `00`.
-   `ss` is the second, with two digits (`00` to `59`). Defaults to
    `00`.
-   `sss` is the millisecond, with three digits (`000` to `999`).
    Defaults to `000`.
-   `Z` is the timezone offset, which can either be the literal
    character `Z` (indicating UTC), or `+` or `-` followed by `HH:mm`,
    the offset in hours and minutes from UTC.

Various components can be omitted, so the following are all valid:

-   Date-only form: `YYYY`, `YYYY-MM`, `YYYY-MM-DD`
-   Date-time form: one of the above date-only forms, followed by `T`,
    followed by `HH:mm`, `HH:mm:ss`, or `HH:mm:ss.sss`. Each combination
    can be followed by a time zone offset.

For example, `"2011-10-10"` (*date-only* form), `"2011-10-10T14:48:00"`
(*date-time* form), or `"2011-10-10T14:48:00.000+09:00"` (*date-time*
form with milliseconds and time zone) are all valid date time strings.

When the time zone offset is absent, **date-only forms are interpreted
as a UTC time and date-time forms are interpreted as local time.** This
is due to a historical spec error that was not consistent with ISO 8601
but could not be changed due to web compatibility. See [Broken Parser --
A Web Reality
Issue](https://maggiepint.com/2017/04/11/fixing-javascript-date-web-compatibility-and-reality/).

[`Date.parse()`](date/parse) and the [`Date()`](date/date) constructor
both accept strings in the date time string format as input.
Furthermore, implementations are allowed to support other date formats
when the input fails to match this format.

The [`toISOString()`](date/toisostring) method returns a string
representation of the date in the date time string format, with the time
zone offset always set to `Z` (UTC).

 
**Note:** You are encouraged to make sure your input conforms to the
date time string format above for maximum compatibility, because support
for other formats is not guaranteed. However, there are some formats
that are supported in all major implementations --- like [RFC
2822](https://datatracker.ietf.org/doc/html/rfc2822) format --- in which
case their usage can be acceptable. Always conduct [cross-browser
tests](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing)
to ensure your code works in all target browsers. A library can help if
many different formats are to be accommodated.


Non-standard strings can be parsed in any way as desired by the
implementation, including the time zone --- most implementations use the
local time zone by default. Implementations are not required to return
invalid date for out-of-bounds date components, although they usually
do. A string may have in-bounds date components (with the bounds defined
above), but does not represent a date in reality (for example,
\"February 30\"). Implementations behave inconsistently in this case.
The [`Date.parse()`](date/parse#examples) page offers more examples
about these non-standard cases.



 
### Other ways to format a date 

 
-   [`toISOString()`](date/toisostring) returns a string in the format
    `1970-01-01T00:00:00.000Z` (the date time string format introduced
    above, which is simplified [ISO
    8601](https://en.wikipedia.org/wiki/ISO_8601)).
    [`toJSON()`](date/tojson) calls `toISOString()` and returns the
    result.
-   [`toString()`](date/tostring) returns a string in the format
    `Thu Jan 01 1970 00:00:00 GMT+0000 (Coordinated Universal Time)`,
    while [`toDateString()`](date/todatestring) and
    [`toTimeString()`](date/totimestring) return the date and time parts
    of the string, respectively.
    [`[@@toPrimitive]()`](date/@@toprimitive) (when passed `"string"` or
    `"default"`) calls `toString()` and returns the result.
-   [`toUTCString()`](date/toutcstring) returns a string in the format
    `Thu, 01 Jan 1970 00:00:00 GMT` (generalized [RFC
    7231](https://datatracker.ietf.org/doc/html/rfc7231)).
-   [`toLocaleDateString()`](date/tolocaledatestring),
    [`toLocaleTimeString()`](date/tolocaletimestring), and
    [`toLocaleString()`](date/tolocalestring) use locale-specific date
    and time formats, usually provided by the [`Intl`](intl) API.

See the [Formats of `toString` method return
values](#formats_of_tostring_method_return_values) section for examples.



 
Constructor
-----------

 

[`Date()`](date/date)

:   When called as a constructor, returns a new `Date` object. When
    called as a function, returns a string representation of the current
    date and time.



 
Static methods 
--------------

 

[`Date.now()`](date/now)

:   Returns the numeric value corresponding to the current time---the
    number of milliseconds elapsed since January 1, 1970 00:00:00 UTC,
    with leap seconds ignored.

[`Date.parse()`](date/parse)

:   Parses a string representation of a date and returns the number of
    milliseconds since 1 January, 1970, 00:00:00 UTC, with leap seconds
    ignored.

[`Date.UTC()`](date/utc)

:   Accepts the same parameters as the longest form of the constructor
    (i.e. 2 to 7) and returns the number of milliseconds since January
    1, 1970, 00:00:00 UTC, with leap seconds ignored.



 
Instance properties 
-------------------

 
These properties are defined on `Date.prototype` and shared by all
`Date` instances.

[`Date.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `Date` instances, the initial value is the [`Date`](date/date)
    constructor.



 
Instance methods 
----------------

 

[`Date.prototype.getDate()`](date/getdate)

:   Returns the day of the month (`1` -- `31`) for the specified date
    according to local time.

[`Date.prototype.getDay()`](date/getday)

:   Returns the day of the week (`0` -- `6`) for the specified date
    according to local time.

[`Date.prototype.getFullYear()`](date/getfullyear)

:   Returns the year (4 digits for 4-digit years) of the specified date
    according to local time.

[`Date.prototype.getHours()`](date/gethours)

:   Returns the hour (`0` -- `23`) in the specified date according to
    local time.

[`Date.prototype.getMilliseconds()`](date/getmilliseconds)

:   Returns the milliseconds (`0` -- `999`) in the specified date
    according to local time.

[`Date.prototype.getMinutes()`](date/getminutes)

:   Returns the minutes (`0` -- `59`) in the specified date according to
    local time.

[`Date.prototype.getMonth()`](date/getmonth)

:   Returns the month (`0` -- `11`) in the specified date according to
    local time.

[`Date.prototype.getSeconds()`](date/getseconds)

:   Returns the seconds (`0` -- `59`) in the specified date according to
    local time.

[`Date.prototype.getTime()`](date/gettime)

:   Returns the numeric value of the specified date as the number of
    milliseconds since January 1, 1970, 00:00:00 UTC. (Negative values
    are returned for prior times.)

[`Date.prototype.getTimezoneOffset()`](date/gettimezoneoffset)

:   Returns the time-zone offset in minutes for the current locale.

[`Date.prototype.getUTCDate()`](date/getutcdate)

:   Returns the day (date) of the month (`1` -- `31`) in the specified
    date according to universal time.

[`Date.prototype.getUTCDay()`](date/getutcday)

:   Returns the day of the week (`0` -- `6`) in the specified date
    according to universal time.

[`Date.prototype.getUTCFullYear()`](date/getutcfullyear)

:   Returns the year (4 digits for 4-digit years) in the specified date
    according to universal time.

[`Date.prototype.getUTCHours()`](date/getutchours)

:   Returns the hours (`0` -- `23`) in the specified date according to
    universal time.

[`Date.prototype.getUTCMilliseconds()`](date/getutcmilliseconds)

:   Returns the milliseconds (`0` -- `999`) in the specified date
    according to universal time.

[`Date.prototype.getUTCMinutes()`](date/getutcminutes)

:   Returns the minutes (`0` -- `59`) in the specified date according to
    universal time.

[`Date.prototype.getUTCMonth()`](date/getutcmonth)

:   Returns the month (`0` -- `11`) in the specified date according to
    universal time.

[`Date.prototype.getUTCSeconds()`](date/getutcseconds)

:   Returns the seconds (`0` -- `59`) in the specified date according to
    universal time.

[`Date.prototype.getYear()`](date/getyear) [Deprecated]

:   Returns the year (usually 2--3 digits) in the specified date
    according to local time. Use [`getFullYear()`](date/getfullyear)
    instead.

[`Date.prototype.setDate()`](date/setdate)

:   Sets the day of the month for a specified date according to local
    time.

[`Date.prototype.setFullYear()`](date/setfullyear)

:   Sets the full year (e.g. 4 digits for 4-digit years) for a specified
    date according to local time.

[`Date.prototype.setHours()`](date/sethours)

:   Sets the hours for a specified date according to local time.

[`Date.prototype.setMilliseconds()`](date/setmilliseconds)

:   Sets the milliseconds for a specified date according to local time.

[`Date.prototype.setMinutes()`](date/setminutes)

:   Sets the minutes for a specified date according to local time.

[`Date.prototype.setMonth()`](date/setmonth)

:   Sets the month for a specified date according to local time.

[`Date.prototype.setSeconds()`](date/setseconds)

:   Sets the seconds for a specified date according to local time.

[`Date.prototype.setTime()`](date/settime)

:   Sets the [`Date`](date) object to the time represented by a number
    of milliseconds since January 1, 1970, 00:00:00 UTC. Use negative
    numbers for times prior.

[`Date.prototype.setUTCDate()`](date/setutcdate)

:   Sets the day of the month for a specified date according to
    universal time.

[`Date.prototype.setUTCFullYear()`](date/setutcfullyear)

:   Sets the full year (e.g. 4 digits for 4-digit years) for a specified
    date according to universal time.

[`Date.prototype.setUTCHours()`](date/setutchours)

:   Sets the hour for a specified date according to universal time.

[`Date.prototype.setUTCMilliseconds()`](date/setutcmilliseconds)

:   Sets the milliseconds for a specified date according to universal
    time.

[`Date.prototype.setUTCMinutes()`](date/setutcminutes)

:   Sets the minutes for a specified date according to universal time.

[`Date.prototype.setUTCMonth()`](date/setutcmonth)

:   Sets the month for a specified date according to universal time.

[`Date.prototype.setUTCSeconds()`](date/setutcseconds)

:   Sets the seconds for a specified date according to universal time.

[`Date.prototype.setYear()`](date/setyear) [Deprecated]

:   Sets the year (usually 2--3 digits) for a specified date according
    to local time. Use [`setFullYear()`](date/setfullyear) instead.

[`Date.prototype.toDateString()`](date/todatestring)

:   Returns the \"date\" portion of the [`Date`](date) as a
    human-readable string like `'Thu Apr 12 2018'`.

[`Date.prototype.toISOString()`](date/toisostring)

:   Converts a date to a string following the ISO 8601 Extended Format.

[`Date.prototype.toJSON()`](date/tojson)

:   Returns a string representing the [`Date`](date) using
    [`toISOString()`](date/toisostring). Intended for use by
    [`JSON.stringify()`](json/stringify).

[`Date.prototype.toLocaleDateString()`](date/tolocaledatestring)

:   Returns a string with a locality sensitive representation of the
    date portion of this date based on system settings.

[`Date.prototype.toLocaleString()`](date/tolocalestring)

:   Returns a string with a locality-sensitive representation of this
    date. Overrides the
    [`Object.prototype.toLocaleString()`](object/tolocalestring) method.

[`Date.prototype.toLocaleTimeString()`](date/tolocaletimestring)

:   Returns a string with a locality-sensitive representation of the
    time portion of this date, based on system settings.

[`Date.prototype.toString()`](date/tostring)

:   Returns a string representing the specified [`Date`](date) object.
    Overrides the [`Object.prototype.toString()`](object/tostring)
    method.

[`Date.prototype.toTimeString()`](date/totimestring)

:   Returns the \"time\" portion of the [`Date`](date) as a
    human-readable string.

[`Date.prototype.toUTCString()`](date/toutcstring)

:   Converts a date to a string using the UTC timezone.

[`Date.prototype.valueOf()`](date/valueof)

:   Returns the primitive value of a [`Date`](date) object. Overrides
    the [`Object.prototype.valueOf()`](object/valueof) method.

[`Date.prototype[@@toPrimitive]()`](date/@@toprimitive)

:   Converts this `Date` object to a primitive value.



 
Examples
--------


 
### Several ways to create a Date object 

 
The following examples show several ways to create JavaScript dates:

 
**Note:** Creating a date from a string has a lot of behavior
inconsistencies. See [date time string format](#date_time_string_format)
for caveats on using different formats.


 
 
[js]


```js
const today = new Date();
const birthday = new Date("December 17, 1995 03:24:00"); // DISCOURAGED: may not work in all runtimes
const birthday2 = new Date("1995-12-17T03:24:00"); // This is standardized and will work reliably
const birthday3 = new Date(1995, 11, 17); // the month is 0-indexed
const birthday4 = new Date(1995, 11, 17, 3, 24, 0);
const birthday5 = new Date(628021800000); // passing epoch timestamp
```




 
### Formats of toString method return values 

 
 
 
[js]


```js
const date = new Date("2020-05-12T23:50:21.817Z");
date.toString(); // Tue May 12 2020 18:50:21 GMT-0500 (Central Daylight Time)
date.toDateString(); // Tue May 12 2020
date.toTimeString(); // 18:50:21 GMT-0500 (Central Daylight Time)
date[Symbol.toPrimitive]("string"); // Tue May 12 2020 18:50:21 GMT-0500 (Central Daylight Time)

date.toISOString(); // 2020-05-12T23:50:21.817Z
date.toJSON(); // 2020-05-12T23:50:21.817Z

date.toUTCString(); // Tue, 12 May 2020 23:50:21 GMT

date.toLocaleString(); // 5/12/2020, 6:50:21 PM
date.toLocaleDateString(); // 5/12/2020
date.toLocaleTimeString(); // 6:50:21 PM
```




 
### To get Date, Month and Year or Time 

 
 
 
[js]


```js
const date = new Date("2000-01-17T16:45:30");
const [month, day, year] = [
  date.getMonth(),
  date.getDate(),
  date.getFullYear(),
];
// [0, 17, 2000] as month are 0-indexed
const [hour, minutes, seconds] = [
  date.getHours(),
  date.getMinutes(),
  date.getSeconds(),
];
// [16, 45, 30]
```




 
### Interpretation of two-digit years 

 
`new Date()` exhibits legacy undesirable, inconsistent behavior with
two-digit year values; specifically, when a `new Date()` call is given a
two-digit year value, that year value does not get treated as a literal
year and used as-is but instead gets interpreted as a relative offset
--- in some cases as an offset from the year `1900`, but in other cases,
as an offset from the year `2000`.

 
 
[js]


```js
let date = new Date(98, 1); // Sun Feb 01 1998 00:00:00 GMT+0000 (GMT)
date = new Date(22, 1); // Wed Feb 01 1922 00:00:00 GMT+0000 (GMT)
date = new Date("2/1/22"); // Tue Feb 01 2022 00:00:00 GMT+0000 (GMT)

// Legacy method; always interprets two-digit year values as relative to 1900
date.setYear(98);
date.toString(); // Sun Feb 01 1998 00:00:00 GMT+0000 (GMT)
date.setYear(22);
date.toString(); // Wed Feb 01 1922 00:00:00 GMT+0000 (GMT)
```


So, to create and get dates between the years `0` and `99`, instead use
the preferred [`setFullYear()`](date/setfullyear) and
[`getFullYear()`](date/getfullyear) methods:.

 
 
[js]


```js
// Preferred method; never interprets any value as being a relative offset,
// but instead uses the year value as-is
date.setFullYear(98);
date.getFullYear(); // 98 (not 1998)
date.setFullYear(22);
date.getFullYear(); // 22 (not 1922, not 2022)
```




 
### Calculating elapsed time 

 
The following examples show how to determine the elapsed time between
two JavaScript dates in milliseconds.

Due to the differing lengths of days (due to daylight saving
changeover), months, and years, expressing elapsed time in units greater
than hours, minutes, and seconds requires addressing a number of issues,
and should be thoroughly researched before being attempted.

 
 
[js]


```js
// Using Date objects
const start = Date.now();

// The event to time goes here:
doSomethingForALongTime();
const end = Date.now();
const elapsed = end - start; // elapsed time in milliseconds
```


 
 
[js]


```js
// Using built-in methods
const start = new Date();

// The event to time goes here:
doSomethingForALongTime();
const end = new Date();
const elapsed = end.getTime() - start.getTime(); // elapsed time in milliseconds
```


 
 
[js]


```js
// To test a function and get back its return
function printElapsedTime(testFn) {
  const startTime = Date.now();
  const result = testFn();
  const endTime = Date.now();

  console.log(`Elapsed time: ${String(endTime - startTime)} milliseconds`);
  return result;
}

const yourFunctionReturn = printElapsedTime(yourFunction);
```


 
**Note:** In browsers that support the [Web Performance
API](https://developer.mozilla.org/en-US/docs/Web/API/performance_property)\'s
high-resolution time feature,
[`Performance.now()`](https://developer.mozilla.org/en-US/docs/Web/API/Performance/now)
can provide more reliable and precise measurements of elapsed time than
[`Date.now()`](date/now).




 
### Get the number of seconds since the ECMAScript Epoch 

 
 
 
[js]


```js
const seconds = Math.floor(Date.now() / 1000);
```


In this case, it\'s important to return only an integer---so a simple
division won\'t do. It\'s also important to only return actually elapsed
seconds. (That\'s why this code uses [`Math.floor()`](math/floor), and
*not* [`Math.round()`](math/round).)



Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date-objects]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date-objects)

  -------------------------------------------------------------------------------------------------------


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

`@@toPrimitive`

47

15

44

34

10

47

44

34

10

5.0

47

1.0

6.0.0

`Date`

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

`UTC`

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

`Date`

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

`getDate`

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

`getDay`

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

`getFullYear`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`getHours`

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

`getMilliseconds`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`getMinutes`

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

`getMonth`

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

`getSeconds`

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

`getTime`

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

`getTimezoneOffset`

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

`getUTCDate`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`getUTCDay`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`getUTCFullYear`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`getUTCHours`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`getUTCMilliseconds`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`getUTCMinutes`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`getUTCMonth`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`getUTCSeconds`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`getYear`

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

`now`

1

12

1

10.5

4

18

4

14

4

1.0

4.4

1.0

0.10.0

`parse`

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

`setDate`

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

`setFullYear`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`setHours`

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

`setMilliseconds`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`setMinutes`

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

`setMonth`

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

`setSeconds`

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

`setTime`

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

`setUTCDate`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`setUTCFullYear`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`setUTCHours`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`setUTCMilliseconds`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`setUTCMinutes`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`setUTCMonth`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`setUTCSeconds`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`setYear`

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

`toDateString`

1

12

1

5

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`toGMTString`

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

`toISOString`

3

12

1

10.5

4

18

4

11

3.2

1.0

≤37

1.0

0.10.0

`toJSON`

3

12

1

10.5

4

18

4

11

3.2

1.0

≤37

1.0

0.10.0

`toLocaleDateString`

1

12

1

5

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

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

`toLocaleTimeString`

1

12

1

5

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`toString`

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

`toTimeString`

1

12

1

5

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`toUTCString`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`valueOf`

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

 
See also 
--------

 
-   [`Date()`](date/date)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date>

