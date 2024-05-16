Date.prototype.getUTCDate()
===========================

 
The `getUTCDate()` method of [`Date`](../date) instances returns the day
of the month for this date according to universal time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
getUTCDate()
```




 
### Parameters

 
None.



 
### Return value 

 
An integer, between 1 and 31, representing day of month for the given
date according to universal time. Returns `NaN` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Examples
--------


 
### Using getUTCDate() 

 
The following example assigns the day of month of the current date to
the variable `dayOfMonth`.

 
 
[js]


```js
const today = new Date();
const dayOfMonth = today.getUTCDate();
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.getutcdate]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.getutcdate)

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

`getUTCDate`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getUTCDate>

