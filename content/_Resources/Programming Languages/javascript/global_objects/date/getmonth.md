Date.prototype.getMonth()
=========================

 
The `getMonth()` method of [`Date`](../date) instances returns the month
for this date according to local time, as a zero-based value (where zero
indicates the first month of the year).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
getMonth()
```




 
### Parameters

 
None.



 
### Return value 

 
An integer, between 0 and 11, representing the month for the given date
according to local time: 0 for January, 1 for February, and so on.
Returns `NaN` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Description
-----------

 
The return value of `getMonth()` is zero-based, which is useful for
indexing into arrays of months, for example:

 
 
[js]


```js
const valentines = new Date("1995-02-14");
const month = valentines.getMonth();
const monthNames = ["January", "February", "March" /* , … */];

console.log(monthNames[month]); // "February"
```


However, for the purpose of internationalization, you should prefer
using [`Intl.DateTimeFormat`](../intl/datetimeformat) with the `options`
parameter instead.

 
 
[js]


```js
const options = { month: "long" };
console.log(new Intl.DateTimeFormat("en-US", options).format(valentines));
// "February"
console.log(new Intl.DateTimeFormat("de-DE", options).format(valentines));
// "Februar"
```




 
Examples
--------


 
### Using getMonth() 

 
The `month` variable has value `11`, based on the value of the
[`Date`](../date) object `xmas95`.

 
 
[js]


```js
const xmas95 = new Date("1995-12-25T23:15:30");
const month = xmas95.getMonth();

console.log(month); // 11
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.getmonth]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.getmonth)

  -----------------------------------------------------------------------------------------------------------------------------


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

`getMonth`

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

 
-   [`Date.prototype.getUTCMonth()`](getutcmonth)
-   [`Date.prototype.setMonth()`](setmonth)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getMonth>

