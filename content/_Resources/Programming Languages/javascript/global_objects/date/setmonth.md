Date.prototype.setMonth()
=========================

 
The `setMonth()` method of [`Date`](../date) instances changes the month
and/or day of the month for this date according to local time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
setMonth(monthValue)
setMonth(monthValue, dateValue)
```




 
### Parameters

 

[`monthValue`](#monthvalue)

:   An integer representing the month: 0 for January, 1 for February,
    and so on.

[`dateValue`](#datevalue) [Optional]

:   An integer from 1 to 31 representing the day of the month.



 
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

 
If you do not specify the `dateValue` parameter, the same value as what
is returned by [`getDate()`](getdate) is used.

If a parameter you specify is outside of the expected range, other
parameters and the date information in the [`Date`](../date) object are
updated accordingly. For example, if you specify 15 for `monthValue`,
the year is incremented by 1, and 3 is used for month.

The current day of month will have an impact on the behavior of this
method. Conceptually it will add the number of days given by the current
day of the month to the 1st day of the new month specified as the
parameter, to return the new date. For example, if the current value is
31st January 2016, calling setMonth with a value of 1 will return 2nd
March 2016. This is because in 2016 February had 29 days.



 
Examples
--------


 
### Using setMonth() 

 
 
 
[js]


```js
const theBigDay = new Date();
theBigDay.setMonth(6);

//Watch out for end of month transitions
const endOfMonth = new Date(2016, 7, 31);
endOfMonth.setMonth(1);
console.log(endOfMonth); //Wed Mar 02 2016 00:00:00
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.setmonth]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.setmonth)

  -----------------------------------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [`Date.prototype.getMonth()`](getmonth)
-   [`Date.prototype.setUTCMonth()`](setutcmonth)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setMonth>

