Date.parse()
============

 
The `Date.parse()` static method parses a string representation of a
date, and returns the date\'s
[timestamp](../date#the_epoch_timestamps_and_invalid_date).

Only the [date time string format](../date#date_time_string_format) is
explicitly specified to be supported. Other formats are
implementation-defined and may not work across all browsers. A library
can help if many different formats are to be accommodated.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Date.parse(dateString)
```




 
### Parameters

 

[`dateString`](#datestring)

:   A string in [the date time string
    format](../date#date_time_string_format). See the linked reference
    for caveats on using different formats.



 
### Return value 

 
A number representing the
[timestamp](../date#the_epoch_timestamps_and_invalid_date) of the given
date. If `dateString` fails to be parsed as a valid date,
[`NaN`](../nan) is returned.



 
Description
-----------

 
This function is useful for setting date values based on string values,
for example in conjunction with the [`setTime()`](settime) method.

Because `parse()` is a static method of `Date`, you always use it as
`Date.parse()`, rather than as a method of a `Date` object you created.



 
Examples
--------


 
### Using Date.parse() 

 
The following calls all return `1546300800000`. The first will imply UTC
time because it\'s date-only, and the others explicitly specify the UTC
timezone.

 
 
[js]


```js
Date.parse("2019-01-01");
Date.parse("2019-01-01T00:00:00.000Z");
Date.parse("2019-01-01T00:00:00.000+00:00");
```


The following call, which does not specify a time zone will be set to
2019-01-01 at 00:00:00 in the local timezone of the system, because it
has both date and time.

 
 
[js]


```js
Date.parse("2019-01-01T00:00:00");
```




 
### Non-standard date strings 

 
 
**Note:** This section contains implementation-specific behavior that
can be inconsistent across implementations.


Implementations usually default to the local time zone when the date
string is non-standard. For consistency, we will assume that the code
uses the UTC timezone.

 
 
[js]


```js
Date.parse("Jan 1, 1970"); // 0 in all implementations

Date.parse("Thu, 01 Jan 1970 00:00:00"); // 0 in all implementations

Date.parse("1970,1,1"); // 0 in Chrome and Firefox, NaN in Safari

Date.parse("02 01 1970");
// 2678400000 in Chrome and Firefox (Sun Feb 01 1970 00:00:00 GMT+0000);
// NaN in Safari

// With explicit timezone
Date.parse("Thu, 01 Jan 1970 00:00:00 GMT+0300");
// -10800000 in all implementations in all timezones

// Single number
Date.parse("0");
// 946684800000 in Chrome (Sat Jan 01 2000 00:00:00 GMT+0000);
// NaN in Firefox;
// -62167219200000 in Safari (Sat Jan 01 0000 00:00:00 GMT+0000)

// Two-digit number that may be a month
Date.parse("28"); // NaN in all implementations

// Two-digit year
Date.parse("70/01/01"); // 0 in all implementations

// Out-of-bounds date components
Date.parse("2014-25-23"); // NaN in all implementations
Date.parse("Mar 32, 2014"); // NaN in all implementations
Date.parse("2014/25/23"); // NaN in all implementations

Date.parse("2014-02-30");
// NaN in Safari and Firefox;
// 1393718400000 in Chrome (Sun Mar 02 2014 00:00:00 GMT+0000)
Date.parse("02/30/2014"); // 1393718400000 in all implementations
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.parse]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.parse)

  ---------------------------------------------------------------------------------------------------


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

`iso_8601`

6

12

4

6

5.1

18

4

10.1

5

1.0

≤37

1.0

0.12.0

 
See also 
--------

 
-   [`Date.UTC()`](utc)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/parse>

