Date.prototype.getUTCSeconds()
==============================

 
The `getUTCSeconds()` method of [`Date`](../date) instances returns the
seconds in the specified date according to universal time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
getUTCSeconds()
```




 
### Parameters

 
None.



 
### Return value 

 
An integer, between 0 and 59, representing the seconds for the given
date according to universal time. Returns `NaN` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Examples
--------


 
### Using getUTCSeconds() 

 
The following example assigns the seconds portion of the current time to
the variable `seconds`.

 
 
[js]


```js
const today = new Date();
const seconds = today.getUTCSeconds();
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.getutcseconds]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.getutcseconds)

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

`getUTCSeconds`

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

 
-   [`Date.prototype.getSeconds()`](getseconds)
-   [`Date.prototype.setUTCSeconds()`](setutcseconds)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getUTCSeconds>

