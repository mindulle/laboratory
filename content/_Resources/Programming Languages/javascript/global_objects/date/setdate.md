Date.prototype.setDate()
========================

 
The `setDate()` method of [`Date`](../date) instances changes the day of
the month for this date according to local time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
setDate(dateValue)
```




 
### Parameters

 

[`dateValue`](#datevalue)

:   An integer representing the day of the month.



 
### Return value 

 
Changes the [`Date`](../date) object in place, and returns its new
[timestamp](../date#the_epoch_timestamps_and_invalid_date). If
`dateValue` is `NaN` (or other values that get
[coerced](../number#number_coercion) to `NaN`, such as `undefined`), the
date is set to [Invalid
Date](../date#the_epoch_timestamps_and_invalid_date) and `NaN` is
returned.



 
Description
-----------

 
If you specify a number outside the expected range, the date information
in the [`Date`](../date) object is updated accordingly. For example, if
the `Date` object holds June 1st, a `dateValue` of 40 changes the date
to July 10th, while a `dateValue` of 0 changes the date to the last day
of the previous month, May 31st.



 
Examples
--------


 
### Using setDate() 

 
 
 
[js]


```js
const theBigDay = new Date(1962, 6, 7, 12); // noon of 1962-07-07 (7th of July 1962, month is 0-indexed)
const theBigDay2 = new Date(theBigDay).setDate(24); // 1962-07-24 (24th of July 1962)
const theBigDay3 = new Date(theBigDay).setDate(32); // 1962-08-01 (1st of August 1962)
const theBigDay4 = new Date(theBigDay).setDate(22); // 1962-07-22 (22nd of July 1962)
const theBigDay5 = new Date(theBigDay).setDate(0); // 1962-06-30 (30th of June 1962)
const theBigDay6 = new Date(theBigDay).setDate(98); // 1962-10-06 (6th of October 1962)
const theBigDay7 = new Date(theBigDay).setDate(-50); // 1962-05-11 (11th of May 1962)
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.setdate]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.setdate)

  ---------------------------------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [`Date()`](date)
-   [`Date.prototype.getDate()`](getdate)
-   [`Date.prototype.setUTCDate()`](setutcdate)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setDate>

