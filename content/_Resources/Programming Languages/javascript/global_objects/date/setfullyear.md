Date.prototype.setFullYear()
============================

 
The `setFullYear()` method of [`Date`](../date) instances changes the
year, month, and/or day of month for this date according to local time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
setFullYear(yearValue)
setFullYear(yearValue, monthValue)
setFullYear(yearValue, monthValue, dateValue)
```




 
### Parameters

 

[`yearValue`](#yearvalue)

:   An integer representing the year. For example, 1995.

[`monthValue`](#monthvalue) [Optional]

:   An integer representing the month: 0 for January, 1 for February,
    and so on.

[`dateValue`](#datevalue) [Optional]

:   An integer between 1 and 31 representing the day of the month. If
    you specify `dateValue`, you must also specify `monthValue`.



 
### Return value 

 
Changes the [`Date`](../date) object in place, and returns its new
[timestamp](../date#the_epoch_timestamps_and_invalid_date). If a
parameter is `NaN` (or other values that get
[coerced](../number#number_coercion) to `NaN`, such as `undefined`), the
date is set to [Invalid
Date](../date#the_epoch_timestamps_and_invalid_date) and `NaN` is
returned.



 
Description
-----------

 
If you do not specify the `monthValue` and `dateValue` parameters, the
same values as what are returned by [`getMonth()`](getmonth) and
[`getDate()`](getdate) are used.

If a parameter you specify is outside of the expected range, other
parameters and the date information in the [`Date`](../date) object are
updated accordingly. For example, if you specify 15 for `monthValue`,
the year is incremented by 1 (`yearValue + 1`), and 3 is used for the
month.



 
Examples
--------


 
### Using setFullYear() 

 
 
 
[js]


```js
const theBigDay = new Date();
theBigDay.setFullYear(1997);
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.setfullyear]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.setfullyear)

  -----------------------------------------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [`Date.prototype.getUTCFullYear()`](getutcfullyear)
-   [`Date.prototype.setUTCFullYear()`](setutcfullyear)
-   [`Date.prototype.setYear()`](setyear)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setFullYear>

