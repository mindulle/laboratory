Intl.DateTimeFormat.prototype.formatRangeToParts()
==================================================

 
The `formatRangeToParts()` method of
[`Intl.DateTimeFormat`](../datetimeformat) instances returns an array of
locale-specific tokens representing each part of the formatted date
range produced by this `Intl.DateTimeFormat` object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
formatRangeToParts(startDate, endDate)
```




 
Examples
--------


 
### Basic formatRangeToParts usage 

 
This method receives two [`Date`](../../date)s and returns an
[`Array`](../../array) of objects containing the *locale-specific*
tokens representing each part of the formatted date range.

 
**Note:** The return values shown in your locale may differ from those
listed below.


 
 
[js]


```js
const date1 = new Date(Date.UTC(1906, 0, 10, 10, 0, 0)); // Wed, 10 Jan 1906 10:00:00 GMT
const date2 = new Date(Date.UTC(1906, 0, 10, 11, 0, 0)); // Wed, 10 Jan 1906 11:00:00 GMT

const fmt = new Intl.DateTimeFormat("en", {
  hour: "numeric",
  minute: "numeric",
});

console.log(fmt.formatRange(date1, date2)); // '10:00 – 11:00 AM'

fmt.formatRangeToParts(date1, date2);
// [
//   { type: 'hour',      value: '10',  source: "startRange" },
//   { type: 'literal',   value: ':',   source: "startRange" },
//   { type: 'minute',    value: '00',  source: "startRange" },
//   { type: 'literal',   value: ' – ', source: "shared"     },
//   { type: 'hour',      value: '11',  source: "endRange"   },
//   { type: 'literal',   value: ':',   source: "endRange"   },
//   { type: 'minute',    value: '00',  source: "endRange"   },
//   { type: 'literal',   value: ' ',   source: "shared"     },
//   { type: 'dayPeriod', value: 'AM',  source: "shared"     }
// ]
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.DateTimeFormat.prototype.formatRangeToParts]](https://tc39.es/ecma402/#sec-Intl.DateTimeFormat.prototype.formatRangeToParts)

  -----------------------------------------------------------------------------------------------------------------------------------------------


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

`formatRangeToParts`

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

 
-   [`Intl.DateTimeFormat.prototype.formatRange()`](formatrange)
-   [`Intl.DateTimeFormat`](../datetimeformat)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/formatRangeToParts>

