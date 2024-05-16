Date.prototype.getFullYear()
============================

 
The `getFullYear()` method of [`Date`](../date) instances returns the
year for this date according to local time.

Use this method instead of the [`getYear()`](getyear) method.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
getFullYear()
```




 
### Parameters

 
None.



 
### Return value 

 
An integer representing the year for the given date according to local
time. Returns `NaN` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Description
-----------

 
Unlike [`getYear()`](getyear), the value returned by `getFullYear()` is
an absolute number. For dates between the years 1000 and 9999,
`getFullYear()` returns a four-digit number, for example, 1995. Use this
function to make sure a year is compliant with years after 2000.



 
Examples
--------


 
### Using getFullYear() 

 
The `fullYear` variable has value `1995`, based on the value of the
[`Date`](../date) object `xmas95`.

 
 
[js]


```js
const xmas95 = new Date("1995-12-25T23:15:30");
const fullYear = xmas95.getFullYear();

console.log(fullYear); // 1995
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.getfullyear]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.getfullyear)

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

`getFullYear`

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

 
-   [`Date.prototype.getUTCFullYear()`](getutcfullyear)
-   [`Date.prototype.setFullYear()`](setfullyear)
-   [`Date.prototype.getYear()`](getyear)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getFullYear>

