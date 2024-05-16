Intl.DateTimeFormat.prototype.formatToParts()
=============================================

 
The `formatToParts()` method of
[`Intl.DateTimeFormat`](../datetimeformat) instances allows locale-aware
formatting of strings produced by this `Intl.DateTimeFormat` object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
formatToParts(date)
```




 
### Parameters

 

[`date`](#date) [Optional]

:   The date to format.



 
### Return value 

 
An [`Array`](../../array) of objects containing the formatted date in
parts.



 
Description
-----------

 
The `formatToParts()` method is useful for custom formatting of date
strings. It returns an [`Array`](../../array) of objects containing the
locale-specific tokens from which it possible to build custom strings
while preserving the locale-specific parts. The structure the
`formatToParts()` method returns, looks like this:

 
 
[js]


```js
[
  { type: "day", value: "17" },
  { type: "weekday", value: "Monday" },
];
```


Possible types are the following:

[`day`](#day)

:   The string used for the day, for example `"17"`.

[`dayPeriod`](#dayperiod)

:   The string used for the day period, for example, `"AM"`, `"PM"`,
    `"in the morning"`, or `"noon"`

[`era`](#era)

:   The string used for the era, for example `"BC"` or `"AD"`.

[`fractionalSecond`](#fractionalsecond)

:   The string used for the fractional seconds, for example `"0"` or
    `"00"` or `"000"`.

[`hour`](#hour)

:   The string used for the hour, for example `"3"` or `"03"`.

[`literal`](#literal)

:   The string used for separating date and time values, for example
    `"/"`, `","`, `"o'clock"`, `"de"`, etc.

[`minute`](#minute)

:   The string used for the minute, for example `"00"`.

[`month`](#month)

:   The string used for the month, for example `"12"`.

[`relatedYear`](#relatedyear)

:   The string used for the related 4-digit Gregorian year, in the event
    that the calendar\'s representation would be a yearName instead of a
    year, for example `"2019"`.

[`second`](#second)

:   The string used for the second, for example `"07"` or `"42"`.

[`timeZone`](#timezone)

:   The string used for the name of the time zone, for example `"UTC"`.
    Default is the timezone of the current environment.

[`weekday`](#weekday)

:   The string used for the weekday, for example `"M"`, `"Monday"`, or
    `"Montag"`.

[`year`](#year)

:   The string used for the year, for example `"2012"` or `"96"`.

[`yearName`](#yearname)

:   The string used for the yearName in relevant contexts, for example
    `"geng-zi"`



 
Examples
--------

 
`DateTimeFormat` outputs localized, opaque strings that cannot be
manipulated directly:

 
 
[js]


```js
const date = Date.UTC(2012, 11, 17, 3, 0, 42);

const formatter = new Intl.DateTimeFormat("en-us", {
  weekday: "long",
  year: "numeric",
  month: "numeric",
  day: "numeric",
  hour: "numeric",
  minute: "numeric",
  second: "numeric",
  fractionalSecondDigits: 3,
  hour12: true,
  timeZone: "UTC",
});

formatter.format(date);
// "Monday, 12/17/2012, 3:00:42.000 AM"
```


However, in many User Interfaces there is a desire to customize the
formatting of this string. The `formatToParts` method enables
locale-aware formatting of strings produced by `DateTimeFormat`
formatters by providing you the string in parts:

 
 
[js]


```js
formatter.formatToParts(date);

// return value:
[
  { type: "weekday", value: "Monday" },
  { type: "literal", value: ", " },
  { type: "month", value: "12" },
  { type: "literal", value: "/" },
  { type: "day", value: "17" },
  { type: "literal", value: "/" },
  { type: "year", value: "2012" },
  { type: "literal", value: ", " },
  { type: "hour", value: "3" },
  { type: "literal", value: ":" },
  { type: "minute", value: "00" },
  { type: "literal", value: ":" },
  { type: "second", value: "42" },
  { type: "fractionalSecond", value: "000" },
  { type: "literal", value: " " },
  { type: "dayPeriod", value: "AM" },
];
```


Now the information is available separately and it can be formatted and
concatenated again in a customized way. For example by using
[`Array.prototype.map()`](../../array/map), [arrow
functions](../../../functions/arrow_functions), a [switch
statement](../../../statements/switch), [template
literals](../../../template_literals), and
[`Array.prototype.join()`](../../array/join).

 
 
[js]


```js
const dateString = formatter
  .formatToParts(date)
  .map(({ type, value }) => {
    switch (type) {
      case "dayPeriod":
        return `<em>${value}</em>`;
      default:
        return value;
    }
  })
  .join("");
```


This will emphasize the day period when using the `formatToParts()`
method.

 
 
[js]


```js
console.log(formatter.format(date));
// "Monday, 12/17/2012, 3:00:42.000 AM"

console.log(dateString);
// "Monday, 12/17/2012, 3:00:42.000 <em>AM</em>"
```




 
### Named Years and Mixed calendars 

 
In some cases, calendars use named years. Chinese and Tibetan calendars,
for example, use a 60-year [sexagenary
cycle](https://en.wikipedia.org/wiki/Sexagenary_cycle) of named years.
These years are disambiguated by relationship to corresponding years on
the Gregorian calendar. When this is the case, the result of
`formatToParts()` will contain an entry for `relatedYear` when a year
would normally be present, containing the 4-digit Gregorian year,
instead of an entry for `year`. Setting an entry in the bag for `year`
(with any value) will yield both the and the `yearName` Gregorian
`relatedYear`:

 
 
[js]


```js
const opts = { year: "numeric", month: "numeric", day: "numeric" };
const df = new Intl.DateTimeFormat("zh-u-ca-chinese", opts);
df.formatToParts(Date.UTC(2012, 11, 17, 3, 0, 42));

// return value
[
  { type: "relatedYear", value: "2012" },
  { type: "literal", value: "年" },
  { type: "month", value: "十一月" },
  { type: "day", value: "4" },
];
```


If the `year` option is not set in the bag (to any value), the result
will include only the `relatedYear`:

 
 
[js]


```js
const df = new Intl.DateTimeFormat("zh-u-ca-chinese");
df.formatToParts(Date.UTC(2012, 11, 17, 3, 0, 42));

// return value
[
  { type: "relatedYear", value: "2012" },
  { type: "literal", value: "年" },
  { type: "month", value: "十一月" },
  { type: "day", value: "4" },
];
```


In cases where the `year` would be output, `.format()` may commonly
present these side-by-side:

 
 
[js]


```js
const df = new Intl.DateTimeFormat("zh-u-ca-chinese", { year: "numeric" });
df.format(Date.UTC(2012, 11, 17, 3, 0, 42)); // 2012壬辰年
```


This also makes it possible to mix locale and calendar in both `format`:

 
 
[js]


```js
const df = new Intl.DateTimeFormat("en-u-ca-chinese", { year: "numeric" });
const date = Date.UTC(2012, 11, 17, 3, 0, 42);
df.format(date); // 2012(ren-chen)
```


And `formatToParts`:

 
 
[js]


```js
const opts = { month: "numeric", day: "numeric", year: "numeric" };
const df = new Intl.DateTimeFormat("en-u-ca-chinese", opts);
const date = Date.UTC(2012, 11, 17, 3);
df.formatToParts(date);
// [
//   { type: 'month', value: '11' },
//   { type: 'literal', value: '/' },
//   { type: 'day', value: '4' },
//   { type: 'literal', value: '/' },
//   { type: 'relatedYear', value: '2012' }
// ]
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.DateTimeFormat.prototype.formatToParts]](https://tc39.es/ecma402/#sec-Intl.DateTimeFormat.prototype.formatToParts)

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

 
See also 
--------

 
-   [`Intl.DateTimeFormat`](../datetimeformat)
-   [`Intl.DateTimeFormat.prototype.format()`](format)
-   [`Date.prototype.toLocaleString()`](../../date/tolocalestring)
-   [`Date.prototype.toLocaleDateString()`](../../date/tolocaledatestring)
-   [`Date.prototype.toLocaleTimeString()`](../../date/tolocaletimestring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/formatToParts>

