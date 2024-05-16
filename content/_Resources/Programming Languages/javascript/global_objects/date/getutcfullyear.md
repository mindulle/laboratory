Date.prototype.getUTCFullYear()
===============================

 
The `getUTCFullYear()` method of [`Date`](../date) instances returns the
year for this date according to universal time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
getUTCFullYear()
```




 
### Parameters

 
None.



 
### Return value 

 
An integer representing the year for the given date according to
universal time. Returns `NaN` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Description
-----------

 
Unlike [`getYear()`](getyear), the value returned by `getUTCFullYear()`
is an absolute number. For dates between the years 1000 and 9999,
`getFullYear()` returns a four-digit number, for example, 1995. Use this
function to make sure a year is compliant with years after 2000.



 
Examples
--------


 
### Using getUTCFullYear() 

 
The following example assigns the four-digit value of the current year
to the variable `year`.

 
 
[js]


```js
const today = new Date();
const year = today.getUTCFullYear();
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.getutcfullyear]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.getutcfullyear)

  -----------------------------------------------------------------------------------------------------------------------------------------


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

`getUTCFullYear`

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

 
-   [`Date.prototype.getFullYear()`](getfullyear)
-   [`Date.prototype.setFullYear()`](setfullyear)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getUTCFullYear>

