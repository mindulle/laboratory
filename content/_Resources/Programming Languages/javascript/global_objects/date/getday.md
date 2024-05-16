Date.prototype.getDay()
=======================

 
The `getDay()` method of [`Date`](../date) instances returns the day of
the week for this date according to local time, where 0 represents
Sunday. For the day of the month, see
[`Date.prototype.getDate()`](getdate).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
getDay()
```




 
### Parameters

 
None.



 
### Return value 

 
An integer, between 0 and 6, representing the day of the week for the
given date according to local time: 0 for Sunday, 1 for Monday, 2 for
Tuesday, and so on. Returns `NaN` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Description
-----------

 
The return value of `getDay()` is zero-based, which is useful for
indexing into arrays of days, for example:

 
 
[js]


```js
const valentines = new Date("1995-02-14");
const day = valentines.getDay();
const dayNames = ["Sunday", "Monday", "Tuesday" /* , … */];

console.log(dayNames[day]); // "Monday"
```


However, for the purpose of internationalization, you should prefer
using [`Intl.DateTimeFormat`](../intl/datetimeformat) with the `options`
parameter instead.

 
 
[js]


```js
const options = { weekday: "long" };
console.log(new Intl.DateTimeFormat("en-US", options).format(valentines));
// "Monday"
console.log(new Intl.DateTimeFormat("de-DE", options).format(valentines));
// "Montag"
```




 
Examples
--------


 
### Using getDay() 

 
The `weekday` variable has value `1`, based on the value of the
[`Date`](../date) object `xmas95`, because December 25, 1995 is a
Monday.

 
 
[js]


```js
const xmas95 = new Date("1995-12-25T23:15:30");
const weekday = xmas95.getDay();

console.log(weekday); // 1
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.getday]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.getday)

  -------------------------------------------------------------------------------------------------------------------------


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

`getDay`

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

 
-   [`Date.prototype.getUTCDate()`](getutcdate)
-   [`Date.prototype.getUTCDay()`](getutcday)
-   [`Date.prototype.setDate()`](setdate)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getDay>

