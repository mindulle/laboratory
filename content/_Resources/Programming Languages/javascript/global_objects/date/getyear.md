Date.prototype.getYear()
========================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


The `getYear()` method of [`Date`](../date) instances returns the year
for this date according to local time. Because `getYear()` does not
return full years (\"year 2000 problem\"), it is deprecated and has been
replaced by the [`getFullYear()`](getfullyear) method.


 
Syntax
------

 
 
 
[js]


```js
getYear()
```




 
### Parameters

 
None.



 
### Return value 

 
An integer representing the year for the given date according to local
time, minus 1900. Returns `NaN` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).

-   For years greater than or equal to 2000, the value is 100 or
    greater. For example, if the year is 2026, `getYear()` returns 126.
-   For years between and including 1900 and 1999, the value returned by
    `getYear()` is between 0 and 99. For example, if the year is 1976,
    `getYear()` returns 76.
-   For years less than 1900, the value returned by `getYear()` is less
    than 0. For example, if the year is 1800, `getYear()` returns -100.

This method essentially returns the value of
[`getFullYear()`](getfullyear) minus 1900. You should use
`getFullYear()` instead, so that the year is specified in full.



 
Examples
--------


 
### Years between 1900 and 1999 

 
The second statement assigns the value 95 to the variable `year`.

 
 
[js]


```js
const xmas = new Date("1995-12-25");
const year = xmas.getYear(); // returns 95
```




 
### Years above 1999 

 
The second statement assigns the value 100 to the variable `year`.

 
 
[js]


```js
const xmas = new Date("2000-12-25");
const year = xmas.getYear(); // returns 100
```




 
### Years below 1900 

 
The second statement assigns the value -100 to the variable `year`.

 
 
[js]


```js
const xmas = new Date("1800-12-25");
const year = xmas.getYear(); // returns -100
```




 
### Setting and getting a year between 1900 and 1999 

 
The third statement assigns the value 95 to the variable `year`,
representing the year 1995.

 
 
[js]


```js
const xmas = new Date("2015-12-25");
xmas.setYear(95);
const year = xmas.getYear(); // returns 95
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.getyear]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#sec-date.prototype.getyear)

  ---------------------------------------------------------------------------------------------------------------------------------------------------------


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

`getYear`

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

 
-   [Polyfill of `Date.prototype.getYear` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-date)
-   [`Date.prototype.getFullYear()`](getfullyear)
-   [`Date.prototype.getUTCFullYear()`](getutcfullyear)
-   [`Date.prototype.setYear()`](setyear)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getYear>

