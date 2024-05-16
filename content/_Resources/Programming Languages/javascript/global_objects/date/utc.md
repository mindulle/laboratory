Date.UTC()
==========

 
The `Date.UTC()` static method accepts parameters representing the date
and time components similar to the [`Date`](../date) constructor, but
treats them as UTC. It returns the number of milliseconds since January
1, 1970, 00:00:00 UTC.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Date.UTC(year)
Date.UTC(year, monthIndex)
Date.UTC(year, monthIndex, day)
Date.UTC(year, monthIndex, day, hour)
Date.UTC(year, monthIndex, day, hour, minute)
Date.UTC(year, monthIndex, day, hour, minute, second)
Date.UTC(year, monthIndex, day, hour, minute, second, millisecond)
```




 
### Parameters

 

[`year`](#year)

:   Integer value representing the year. Values from `0` to `99` map to
    the years `1900` to `1999`. All other values are the actual year.
    See the [example](../date#interpretation_of_two-digit_years).

[`monthIndex`](#monthindex) [Optional]

:   Integer value representing the month, beginning with `0` for January
    to `11` for December. Defaults to `0`.

[`day`](#day) [Optional]

:   Integer value representing the day of the month. Defaults to `1`.

[`hours`](#hours) [Optional]

:   Integer value between `0` and `23` representing the hour of the day.
    Defaults to `0`.

[`minutes`](#minutes) [Optional]

:   Integer value representing the minute segment of a time. Defaults to
    `0`.

[`seconds`](#seconds) [Optional]

:   Integer value representing the second segment of a time. Defaults to
    `0`.

[`milliseconds`](#milliseconds) [Optional]

:   Integer value representing the millisecond segment of a time.
    Defaults to `0`.



 
### Return value 

 
A number representing the
[timestamp](../date#the_epoch_timestamps_and_invalid_date) of the given
date. Returns `NaN` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Description
-----------

 
Years between `0` and `99` are converted to a year in the 20th century
`(1900 + year)`. For example, `95` is converted to the year `1995`.

The `UTC()` method differs from the [`Date()`](date) constructor in
three ways:

1.  `Date.UTC()` uses universal time instead of the local time.
2.  `Date.UTC()` returns a time value as a number instead of creating a
    [`Date`](../date) object.
3.  When passed a single number, `Date.UTC()` interprets it as a year
    instead of a timestamp.

If a parameter is outside of the expected range, the `UTC()` method
updates the other parameters to accommodate the value. For example, if
`15` is used for `monthIndex`, the year will be incremented by 1
`(year + 1)` and `3` will be used for the month.

Because `UTC()` is a static method of `Date`, you always use it as
`Date.UTC()`, rather than as a method of a `Date` object you created.



 
Examples
--------


 
### Using Date.UTC() 

 
The following statement creates a [`Date`](../date) object with the
arguments treated as UTC instead of local:

 
 
[js]


```js
const utcDate = new Date(Date.UTC(2018, 11, 1, 0, 0, 0));
```




 
### Behavior of Date.UTC() with one argument 

 
`Date.UTC()` when passed one argument used to have inconsistent
behavior, because implementations only kept the behavior consistent with
the [`Date()`](date) constructor, which does not interpret a single
argument as the year number. Implementations are now required to treat
omitted `monthIndex` as `0`, instead of coercing it to `NaN`.

 
 
[js]


```js
Date.UTC(2017); // 1483228800000
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.utc]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.utc)

  -----------------------------------------------------------------------------------------------


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

`optional_monthIndex`

57

79

54

44

12

57

54

43

12

7.0

57

1.0

8.0.0

 
See also 
--------

 
-   [`Date.parse()`](parse)
-   [`Date`](../date)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/UTC>

