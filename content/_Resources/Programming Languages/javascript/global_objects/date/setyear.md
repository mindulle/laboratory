Date.prototype.setYear()
========================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


The `setYear()` method of [`Date`](../date) instances sets the year for
a specified date according to local time.

However, the way the legacy `setYear()` method sets year values is
different from how the preferred [`setFullYear()`](setfullyear) method
sets year values --- and in some cases, also different from how
`new Date()` and [`Date.parse()`](parse) set year values. Specifically,
given two-digit numbers, such as `22` and `61`:

-   `setYear()` interprets any two-digit number as an offset to `1900`;
    so `date.setYear(22)` results in the year value being set to `1922`,
    and `date.setYear(61)` results in the year value being set to
    `1961`. (In contrast, while `new Date(61, 1)` also results in the
    year value being set to `1961`, `new Date("2/1/22")` results in the
    year value being set to `2022`; and similarly for
    [`Date.parse()`](parse)).
-   [`setFullYear()`](setfullyear) does no special interpretation but
    instead uses the literal two-digit value as-is to set the year; so
    `date.setFullYear(61)` results in the year value being set to
    `0061`, and `date.setFullYear(22)` results in the year value being
    set to `0022`.

Because of those differences in behavior, you should no longer use the
legacy `setYear()` method, but should instead use the preferred
[`setFullYear()`](setfullyear) method.


 
Syntax
------

 
 
 
[js]


```js
setYear(yearValue)
```




 
### Parameters

 

[`yearValue`](#yearvalue)

:   An integer.



 
### Return value 

 
Changes the [`Date`](../date) object in place, and returns its new
[timestamp](../date#the_epoch_timestamps_and_invalid_date). If
`yearValue` is `NaN` (or other values that get
[coerced](../number#number_coercion) to `NaN`, such as `undefined`), the
date is set to [Invalid
Date](../date#the_epoch_timestamps_and_invalid_date) and `NaN` is
returned.



 
Description
-----------

 
If `yearValue` is a number between 0 and 99 (inclusive), then the year
for `dateObj` is set to `1900 + yearValue`. Otherwise, the year for
`dateObj` is set to `yearValue`.



 
Examples
--------


 
### Using setYear() 

 
The first two lines set the year to 1996. The third sets the year to
2000.

 
 
[js]


```js
const theBigDay = new Date();

theBigDay.setYear(96);
theBigDay.setYear(1996);
theBigDay.setYear(2000);
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.setyear]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#sec-date.prototype.setyear)

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

`setYear`

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

 
-   [Polyfill of `Date.prototype.setYear` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-date)
-   [`Date.prototype.getFullYear()`](getfullyear)
-   [`Date.prototype.getUTCFullYear()`](getutcfullyear)
-   [`Date.prototype.setFullYear()`](setfullyear)
-   [`Date.prototype.setUTCFullYear()`](setutcfullyear)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setYear>

