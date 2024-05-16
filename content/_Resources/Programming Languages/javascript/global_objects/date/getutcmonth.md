Date.prototype.getUTCMonth()
============================

 
The `getUTCMonth()` method of [`Date`](../date) instances returns the
month for this date according to universal time, as a zero-based value
(where zero indicates the first month of the year).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
getUTCMonth()
```




 
### Parameters

 
None.



 
### Return value 

 
An integer, between 0 and 11, representing the month for the given date
according to universal time: 0 for January, 1 for February, and so on.
Returns `NaN` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Examples
--------


 
### Using getUTCMonth() 

 
The following example assigns the month portion of the current date to
the variable `month`.

 
 
[js]


```js
const today = new Date();
const month = today.getUTCMonth();
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.getutcmonth]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.getutcmonth)

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

`getUTCMonth`

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

 
-   [`Date.prototype.getMonth()`](getmonth)
-   [`Date.prototype.setUTCMonth()`](setutcmonth)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getUTCMonth>

