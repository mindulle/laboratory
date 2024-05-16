Date.prototype.toTimeString()
=============================

 
The `toTimeString()` method of [`Date`](../date) instances returns a
string representing the time portion of this date interpreted in the
local timezone.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toTimeString()
```




 
### Parameters

 
None.



 
### Return value 

 
A string representing the time portion of the given date (see
description for the format). Returns `"Invalid Date"` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Description
-----------

 
[`Date`](../date) instances refer to a specific point in time.
`toTimeString()` interprets the date in the local timezone and formats
the *time* part in English. It always uses the format of
`hh:mm:ss GMT±xxxx (TZ)`, where:

 
  Format String   Description
  --------------- ----------------------------------------------------------------------------------------------------------
  `hh`            Hour, as two digits with leading zero if required
  `mm`            Minute, as two digits with leading zero if required
  `ss`            Seconds, as two digits with leading zero if required
  `±xxxx`         The local timezone\'s offset --- two digits for hours and two digits for minutes (e.g. `-0500`, `+0800`)
  `TZ`            The timezone\'s name (e.g. `PDT`, `PST`)


For example: \"04:42:04 GMT+0000 (Coordinated Universal Time)\".

-   If you only want to get the *date* part, use
    [`toDateString()`](todatestring).
-   If you want to get both the date and time, use
    [`toString()`](tostring).
-   If you want to make the date interpreted as UTC instead of local
    timezone, use [`toUTCString()`](toutcstring).
-   If you want to format the date in a more user-friendly format (e.g.
    localization), use [`toLocaleTimeString()`](tolocaletimestring).



 
Examples
--------


 
### Using toTimeString() 

 
 
 
[js]


```js
const d = new Date(0);

console.log(d.toString()); // "Thu Jan 01 1970 00:00:00 GMT+0000 (Coordinated Universal Time)"
console.log(d.toTimeString()); // "00:00:00 GMT+0000 (Coordinated Universal Time)"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.totimestring]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.totimestring)

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

`toTimeString`

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

 
-   [`Date.prototype.toLocaleTimeString()`](tolocaletimestring)
-   [`Date.prototype.toDateString()`](todatestring)
-   [`Date.prototype.toString()`](tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toTimeString>

