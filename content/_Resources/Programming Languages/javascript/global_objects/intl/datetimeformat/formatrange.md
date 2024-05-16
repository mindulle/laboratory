Intl.DateTimeFormat.prototype.formatRange()
===========================================

 
The `formatRange()` method of [`Intl.DateTimeFormat`](../datetimeformat)
instances formats a date range in the most concise way based on the
locales and options provided when instantiating this
`Intl.DateTimeFormat` object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
formatRange(startDate, endDate)
```




 
### Parameters

 

[`startDate`](#startdate)

:   A [`Date`](../../date) object representing the start of the date
    range.

[`endDate`](#enddate)

:   A [`Date`](../../date) object representing the end of the date
    range.



 
### Return value 

 
A string representing the given date range formatted according to the
locale and formatting options of this
[`Intl.DateTimeFormat`](../datetimeformat) object.



 
Examples
--------


 
### Basic formatRange usage 

 
This method receives two [`Date`](../../date)s and formats the date
range in the most concise way based on the `locale` and `options`
provided when instantiating [`Intl.DateTimeFormat`](../datetimeformat).

 
 
[js]


```js
const date1 = new Date(Date.UTC(1906, 0, 10, 10, 0, 0)); // Wed, 10 Jan 1906 10:00:00 GMT
const date2 = new Date(Date.UTC(1906, 0, 10, 11, 0, 0)); // Wed, 10 Jan 1906 11:00:00 GMT
const date3 = new Date(Date.UTC(1906, 0, 20, 10, 0, 0)); // Sat, 20 Jan 1906 10:00:00 GMT

const fmt1 = new Intl.DateTimeFormat("en", {
  year: "2-digit",
  month: "numeric",
  day: "numeric",
  hour: "numeric",
  minute: "numeric",
});
console.log(fmt1.format(date1)); // '1/10/06, 10:00 AM'
console.log(fmt1.formatRange(date1, date2)); // '1/10/06, 10:00 – 11:00 AM'
console.log(fmt1.formatRange(date1, date3)); // '1/10/06, 10:00 AM – 1/20/07, 10:00 AM'

const fmt2 = new Intl.DateTimeFormat("en", {
  year: "numeric",
  month: "short",
  day: "numeric",
});
console.log(fmt2.format(date1)); // 'Jan 10, 1906'
console.log(fmt2.formatRange(date1, date2)); // 'Jan 10, 1906'
console.log(fmt2.formatRange(date1, date3)); // 'Jan 10 – 20, 1906'
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.datetimeformat.prototype.formatRange]](https://tc39.es/ecma402/#sec-intl.datetimeformat.prototype.formatRange)

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

`formatRange`

76

79

91

63

14.1

76

91

54

14.5

12.0

76

1.8

12.9.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `DateTimeFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/DateTimeFormat)
for more details.

 
See also 
--------

 
-   [`Intl.DateTimeFormat`](../datetimeformat)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/formatRange>

