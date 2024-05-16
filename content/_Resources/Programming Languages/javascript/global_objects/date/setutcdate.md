Date.prototype.setUTCDate()
===========================

 
The `setUTCDate()` method of [`Date`](../date) instances changes the day
of the month for this date according to universal time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
setUTCDate(dateValue)
```




 
### Parameters

 

[`dateValue`](#datevalue)

:   An integer from 1 to 31 representing the day of the month.



 
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

 
If the `dateValue` is outside of the range of date values for the month,
`setDate()` will update the [`Date`](../date) object accordingly.

For example, if 0 is provided for `dateValue`, the date will be set to
the last day of the previous month. If you use 40 for `dateValue`, and
the month stored in the [`Date`](../date) object is June, the day will
be changed to 10 and the month will be incremented to July.

If a negative number is provided for `dateValue`, the date will be set
counting backwards from the last day of the previous month. -1 would
result in the date being set to 1 day before the last day of the
previous month.



 
Examples
--------


 
### Using setUTCDate() 

 
 
 
[js]


```js
const theBigDay = new Date();
theBigDay.setUTCDate(20);
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.setutcdate]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.setutcdate)

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

`setUTCDate`

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

 
-   [`Date.prototype.getUTCDate()`](getutcdate)
-   [`Date.prototype.setDate()`](setdate)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setUTCDate>

