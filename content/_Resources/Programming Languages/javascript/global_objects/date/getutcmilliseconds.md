Date.prototype.getUTCMilliseconds()
===================================

 
The `getUTCMilliseconds()` method of [`Date`](../date) instances returns
the milliseconds for this date according to universal time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
getUTCMilliseconds()
```




 
### Parameters

 
None.



 
### Return value 

 
An integer, between 0 and 999, representing the milliseconds for the
given date according to universal time. Returns `NaN` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).

Not to be confused with the timestamp. To get the total milliseconds
since the epoch, use the [`getTime()`](gettime) method.



 
Examples
--------


 
### Using getUTCMilliseconds() 

 
The following example assigns the milliseconds portion of the current
time to the variable `milliseconds`.

 
 
[js]


```js
const today = new Date();
const milliseconds = today.getUTCMilliseconds();
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.getutcmilliseconds]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.getutcmilliseconds)

  -------------------------------------------------------------------------------------------------------------------------------------------------


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

`getUTCMilliseconds`

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

 
-   [`Date.prototype.getMilliseconds()`](getmilliseconds)
-   [`Date.prototype.setUTCMilliseconds()`](setutcmilliseconds)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getUTCMilliseconds>

