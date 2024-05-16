Date.prototype.setUTCMonth()
============================

 
The `setUTCMonth()` method of [`Date`](../date) instances changes the
month and/or day of the month for this date according to universal time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
setUTCMonth(monthValue)
setUTCMonth(monthValue, dateValue)
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

 
If you do not specify the `dateValue` parameter, the value returned from
the [`getUTCDate()`](getutcdate) method is used.

If a parameter you specify is outside of the expected range,
`setUTCMonth()` attempts to update the date information in the
[`Date`](../date) object accordingly. For example, if you use 15 for
`monthValue`, the year will be incremented by 1, and 3 will be used for
month.



 
Examples
--------


 
### Using setUTCMonth() 

 
 
 
[js]


```js
const theBigDay = new Date();
theBigDay.setUTCMonth(11);
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.setutcmonth]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.setutcmonth)

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

 
See also 
--------

 
-   [`Date.prototype.getUTCMonth()`](getutcmonth)
-   [`Date.prototype.setMonth()`](setmonth)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setUTCMonth>

