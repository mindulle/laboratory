Date.prototype.setTime()
========================

 
The `setTime()` method of [`Date`](../date) instances changes the
[timestamp](../date#the_epoch_timestamps_and_invalid_date) for this
date, which is the number of milliseconds since the
[epoch](../date#the_epoch_timestamps_and_invalid_date), defined as the
midnight at the beginning of January 1, 1970, UTC.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
setTime(timeValue)
```




 
### Parameters

 

[`timeValue`](#timevalue)

:   An integer representing the new timestamp --- the number of
    milliseconds since the midnight at the beginning of January 1, 1970,
    UTC.



 
### Return value 

 
Changes the [`Date`](../date) object in place, and returns its new
[timestamp](../date#the_epoch_timestamps_and_invalid_date). If
`timeValue` is `NaN` (or other values that get
[coerced](../number#number_coercion) to `NaN`, such as `undefined`), the
date is set to [Invalid
Date](../date#the_epoch_timestamps_and_invalid_date) and `NaN` is
returned.



 
Examples
--------


 
### Using setTime() 

 
 
 
[js]


```js
const theBigDay = new Date("1999-07-01");
const sameAsBigDay = new Date();
sameAsBigDay.setTime(theBigDay.getTime());
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.settime]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.settime)

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

`setTime`

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

 
-   [`Date.prototype.getTime()`](gettime)
-   [`Date.prototype.setUTCHours()`](setutchours)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setTime>

