Date.prototype.toISOString()
============================

 
The `toISOString()` method of [`Date`](../date) instances returns a
string representing this date in the [date time string
format](../date#date_time_string_format), a *simplified* format based on
[ISO 8601](https://en.wikipedia.org/wiki/ISO_8601), which is always 24
or 27 characters long (`YYYY-MM-DDTHH:mm:ss.sssZ` or
`±YYYYYY-MM-DDTHH:mm:ss.sssZ`, respectively). The timezone is always
UTC, as denoted by the suffix `Z`.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toISOString()
```




 
### Parameters

 
None.



 
### Return value 

 
A string representing the given date in the [date time string
format](../date#date_time_string_format) according to universal time.
It\'s the same format as the one required to be recognized by
[`Date.parse()`](parse).



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if the date is
    [invalid](../date#the_epoch_timestamps_and_invalid_date) or if it
    corresponds to a year that cannot be represented in the date string
    format.



 
Examples
--------


 
### Using toISOString() 

 
 
 
[js]


```js
const d = new Date(0);

console.log(d.toISOString()); // "1970-01-01T00:00:00.000Z"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.toisostring]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.toisostring)

  -----------------------------------------------------------------------------------------------------------------------------------


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

`toISOString`

3

12

1

10.5

4

18

4

11

3.2

1.0

≤37

1.0

0.10.0

 
See also 
--------

 
-   [`Date.prototype.toLocaleDateString()`](tolocaledatestring)
-   [`Date.prototype.toString()`](tostring)
-   [`Date.prototype.toUTCString()`](toutcstring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toISOString>

