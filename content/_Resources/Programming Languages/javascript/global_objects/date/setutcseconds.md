Date.prototype.setUTCSeconds()
==============================

 
The `setUTCSeconds()` method of [`Date`](../date) instances changes the
seconds and/or milliseconds for this date according to universal time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
setUTCSeconds(secondsValue)
setUTCSeconds(secondsValue, msValue)
```




 
### Parameters

 

[`secondsValue`](#secondsvalue)

:   An integer between 0 and 59 representing the seconds.

[`msValue`](#msvalue) [Optional]

:   An integer between 0 and 999 representing the milliseconds.



 
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

 
If you do not specify the `msValue` parameter, the value returned from
the [`getUTCMilliseconds()`](getutcmilliseconds) method is used.

If a parameter you specify is outside of the expected range,
`setUTCSeconds()` attempts to update the date information in the
[`Date`](../date) object accordingly. For example, if you use 100 for
`secondsValue`, the minutes stored in the [`Date`](../date) object will
be incremented by 1, and 40 will be used for seconds.



 
Examples
--------


 
### Using setUTCSeconds() 

 
 
 
[js]


```js
const theBigDay = new Date();
theBigDay.setUTCSeconds(20);
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.setutcseconds]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.setutcseconds)

  ---------------------------------------------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [`Date.prototype.getUTCSeconds()`](getutcseconds)
-   [`Date.prototype.setSeconds()`](setseconds)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setUTCSeconds>

