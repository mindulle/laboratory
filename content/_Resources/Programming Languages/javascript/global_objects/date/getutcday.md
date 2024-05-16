Date.prototype.getUTCDay()
==========================

 
The `getUTCDay()` method of [`Date`](../date) instances returns the day
of the week for this date according to universal time, where 0
represents Sunday.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
getUTCDay()
```




 
### Parameters

 
None.



 
### Return value 

 
An integer corresponding to the day of the week for the given date
according to universal time: 0 for Sunday, 1 for Monday, 2 for Tuesday,
and so on. Returns `NaN` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Examples
--------


 
### Using getUTCDay() 

 
The following example assigns the weekday portion of the current date to
the variable `weekday`.

 
 
[js]


```js
const today = new Date();
const weekday = today.getUTCDay();
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.getutcday]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.getutcday)

  -------------------------------------------------------------------------------------------------------------------------------


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

`getUTCDay`

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
-   [`Date.prototype.getDay()`](getday)
-   [`Date.prototype.setUTCDate()`](setutcdate)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getUTCDay>

