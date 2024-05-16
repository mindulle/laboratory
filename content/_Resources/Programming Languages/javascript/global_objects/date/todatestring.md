Date.prototype.toDateString()
=============================

 
The `toDateString()` method of [`Date`](../date) instances returns a
string representing the date portion of this date interpreted in the
local timezone.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toDateString()
```




 
### Parameters

 
None.



 
### Return value 

 
A string representing the date portion of the given date (see
description for the format). Returns `"Invalid Date"` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Description
-----------

 
[`Date`](../date) instances refer to a specific point in time.
`toDateString()` interprets the date in the local timezone and formats
the *date* part in English. It always uses the following format,
separated by spaces:

1.  First three letters of the week day name
2.  First three letters of the month name
3.  Two-digit day of the month, padded on the left a zero if necessary
4.  Four-digit year (at least), padded on the left with zeros if
    necessary. May have a negative sign

For example: \"Thu Jan 01 1970\".

-   If you only want to get the *time* part, use
    [`toTimeString()`](totimestring).
-   If you want to get both the date and time, use
    [`toString()`](tostring).
-   If you want to make the date interpreted as UTC instead of local
    timezone, use [`toUTCString()`](toutcstring).
-   If you want to format the date in a more user-friendly format (e.g.
    localization), use [`toLocaleTimeString()`](tolocaletimestring).



 
Examples
--------


 
### Using toDateString() 

 
 
 
[js]


```js
const d = new Date(0);

console.log(d.toString()); // "Thu Jan 01 1970 00:00:00 GMT+0000 (Coordinated Universal Time)"
console.log(d.toDateString()); // "Thu Jan 01 1970"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.todatestring]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.todatestring)

  -------------------------------------------------------------------------------------------------------------------------------------


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

`toDateString`

1

12

1

5

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

 
-   [`Date.prototype.toLocaleDateString()`](tolocaledatestring)
-   [`Date.prototype.toTimeString()`](totimestring)
-   [`Date.prototype.toString()`](tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toDateString>

