Intl.DateTimeFormat.prototype.format()
======================================

 
The `format()` method of [`Intl.DateTimeFormat`](../datetimeformat)
instances formats a date according to the locale and formatting options
of this `Intl.DateTimeFormat` object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
format(date)
```




 
### Parameters

 

[`date`](#date)

:   The date to format.



 
### Return value 

 
A string representing the given `date` formatted according to the locale
and formatting options of this
[`Intl.DateTimeFormat`](../datetimeformat) object.



 
Examples
--------


 
### Using format 

 
Use the `format` getter function for formatting a single date, here for
Serbia:

 
 
[js]


```js
const options = {
  weekday: "long",
  year: "numeric",
  month: "long",
  day: "numeric",
};
const dateTimeFormat = new Intl.DateTimeFormat("sr-RS", options);
console.log(dateTimeFormat.format(new Date()));
// "недеља, 7. април 2013."
```




 
### Using format with map 

 
Use the `format` getter function for formatting all dates in an array.
Note that the function is bound to the
[`Intl.DateTimeFormat`](../datetimeformat) from which it was obtained,
so it can be passed directly to
[`Array.prototype.map()`](../../array/map).

 
 
[js]


```js
const a = [new Date(2012, 8), new Date(2012, 11), new Date(2012, 3)];
const options = { year: "numeric", month: "long" };
const dateTimeFormat = new Intl.DateTimeFormat("pt-BR", options);
const formatted = a.map(dateTimeFormat.format);
console.log(formatted.join("; "));
// "setembro de 2012; dezembro de 2012; abril de 2012"
```




 
### Avoid comparing formatted date values to static values 

 
Most of the time, the formatting returned by `format()` is consistent.
However, this might change in the future and isn\'t guaranteed for all
the languages --- output variations are by design and allowed by the
specification. Most notably, the IE and Edge browsers insert
bidirectional control characters around dates, so the output text will
flow properly when concatenated with other text.

For this reason you cannot expect to be able to compare the results of
`format()` to a static value:

 
 
[js]


```js
let d = new Date("2019-01-01T00:00:00.000000Z");
let formattedDate = Intl.DateTimeFormat(undefined, {
  year: "numeric",
  month: "numeric",
  day: "numeric",
  hour: "numeric",
  minute: "numeric",
  second: "numeric",
}).format(d);

"1.1.2019, 01:00:00" === formattedDate;
// true in Firefox and others
// false in IE and Edge
```


 
**Note:** See also this [StackOverflow
thread](https://stackoverflow.com/questions/25574963/ies-tolocalestring-has-strange-characters-in-results)
for more details and examples.




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.datetimeformat.prototype.format]](https://tc39.es/ecma402/#sec-intl.datetimeformat.prototype.format)

  -----------------------------------------------------------------------------------------------------------------------


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

`format`

24

12

29

15

10

25

56

14

10

1.5

4.4

1.8

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `DateTimeFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/DateTimeFormat)
for more details.

 
See also 
--------

 
-   [`Intl.DateTimeFormat`](../datetimeformat)
-   [`Date.prototype.toLocaleString()`](../../date/tolocalestring)
-   [`Date.prototype.toLocaleDateString()`](../../date/tolocaledatestring)
-   [`Date.prototype.toLocaleTimeString()`](../../date/tolocaletimestring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/format>

