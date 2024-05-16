Date.prototype.getSeconds()
===========================

 
The `getSeconds()` method of [`Date`](../date) instances returns the
seconds for this date according to local time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
getSeconds()
```




 
### Parameters

 
None.



 
### Return value 

 
An integer, between 0 and 59, representing the seconds for the given
date according to local time. Returns `NaN` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Examples
--------


 
### Using getSeconds() 

 
The `seconds` variable has value `30`, based on the value of the
[`Date`](../date) object `xmas95`.

 
 
[js]


```js
const xmas95 = new Date("1995-12-25T23:15:30");
const seconds = xmas95.getSeconds();

console.log(seconds); // 30
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.getseconds]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.getseconds)

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

`getSeconds`

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

 
-   [`Date.prototype.getUTCSeconds()`](getutcseconds)
-   [`Date.prototype.setSeconds()`](setseconds)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getSeconds>

