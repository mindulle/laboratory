Date.prototype.setMinutes()
===========================

 
The `setMinutes()` method of [`Date`](../date) instances changes the
minutes for this date according to local time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
setMinutes(minutesValue)
setMinutes(minutesValue, secondsValue)
setMinutes(minutesValue, secondsValue, msValue)
```




 
### Parameters

 

[`minutesValue`](#minutesvalue)

:   An integer between 0 and 59 representing the minutes.

[`secondsValue`](#secondsvalue) [Optional]

:   An integer between 0 and 59 representing the seconds. If you specify
    `secondsValue`, you must also specify `minutesValue`.

[`msValue`](#msvalue) [Optional]

:   An integer between 0 and 999 representing the milliseconds. If you
    specify `msValue`, you must also specify `minutesValue` and
    `secondsValue`.



 
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

 
If you do not specify the `secondsValue` and `msValue` parameters, the
same values as what are returned by [`getSeconds()`](getseconds) and
[`getMilliseconds()`](getmilliseconds) are used.

If a parameter you specify is outside of the expected range, other
parameters and the date information in the [`Date`](../date) object are
updated accordingly. For example, if you specify 100 for `secondsValue`,
the minutes is incremented by 1 (`minutesValue + 1`), and 40 is used for
seconds.



 
Examples
--------


 
### Using setMinutes() 

 
 
 
[js]


```js
const theBigDay = new Date();
theBigDay.setMinutes(45);
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.setminutes]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.setminutes)

  ---------------------------------------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [`Date.prototype.getMinutes()`](getminutes)
-   [`Date.prototype.setUTCMinutes()`](setutcminutes)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setMinutes>

