Date.prototype.setUTCHours()
============================

 
The `setUTCHours()` method of [`Date`](../date) instances changes the
hours, minutes, seconds, and/or milliseconds for this date according to
universal time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
setUTCHours(hoursValue)
setUTCHours(hoursValue, minutesValue)
setUTCHours(hoursValue, minutesValue, secondsValue)
setUTCHours(hoursValue, minutesValue, secondsValue, msValue)
```




 
### Parameters

 

[`hoursValue`](#hoursvalue)

:   An integer between 0 and 23 representing the hours.

[`minutesValue`](#minutesvalue) [Optional]

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

 
If you do not specify the `minutesValue`, `secondsValue`, and `msValue`
parameters, the values returned from the
[`getUTCMinutes()`](getutcminutes), [`getUTCSeconds()`](getutcseconds),
and [`getUTCMilliseconds()`](getutcmilliseconds) methods are used.

If a parameter you specify is outside of the expected range,
`setUTCHours()` attempts to update the date information in the
[`Date`](../date) object accordingly. For example, if you use 100 for
`secondsValue`, the minutes will be incremented by 1
(`minutesValue + 1`), and 40 will be used for seconds.



 
Examples
--------


 
### Using setUTCHours() 

 
 
 
[js]


```js
const theBigDay = new Date();
theBigDay.setUTCHours(8);
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.setutchours]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.setutchours)

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

 
See also 
--------

 
-   [`Date.prototype.getUTCHours()`](getutchours)
-   [`Date.prototype.setHours()`](sethours)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setUTCHours>

