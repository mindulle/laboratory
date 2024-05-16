Date.prototype.toString()
=========================

 
The `toString()` method of [`Date`](../date) instances returns a string
representing this date interpreted in the local timezone.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toString()
```




 
### Parameters

 
None.



 
### Return value 

 
A string representing the given date (see description for the format).
Returns `"Invalid Date"` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Description
-----------

 
The `toString()` method is part of the [type coercion
protocol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#type_coercion).
Because `Date` has a [`[@@toPrimitive]()`](@@toprimitive) method, that
method always takes priority over `toString()` when a `Date` object is
implicitly [coerced to a string](../string#string_coercion). However,
`Date.prototype[@@toPrimitive]()` still calls `this.toString()`
internally.

The [`Date`](../date) object overrides the
[`toString()`](../object/tostring) method of [`Object`](../object).
`Date.prototype.toString()` returns a string representation of the Date
as interpreted in the local timezone, containing both the date and the
time --- it joins the string representation specified in
[`toDateString()`](todatestring) and [`toTimeString()`](totimestring)
together, adding a space in between. For example: \"Thu Jan 01 1970
00:00:00 GMT+0000 (Coordinated Universal Time)\".

`Date.prototype.toString()` must be called on [`Date`](../date)
instances. If the `this` value does not inherit from `Date.prototype`, a
[`TypeError`](../typeerror) is thrown.

-   If you only want to get the *date* part, use
    [`toDateString()`](todatestring).
-   If you only want to get the *time* part, use
    [`toTimeString()`](totimestring).
-   If you want to make the date interpreted as UTC instead of local
    timezone, use [`toUTCString()`](toutcstring).
-   If you want to format the date in a more user-friendly format (e.g.
    localization), use [`toLocaleString()`](tolocalestring).



 
Examples
--------


 
### Using toString() 

 
 
 
[js]


```js
const d = new Date(0);
console.log(d.toString()); // "Thu Jan 01 1970 00:00:00 GMT+0000 (Coordinated Universal Time)"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.tostring]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.tostring)

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

`toString`

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

 
-   [`Object.prototype.toString()`](../object/tostring)
-   [`Date.prototype.toDateString()`](todatestring)
-   [`Date.prototype.toLocaleString()`](tolocalestring)
-   [`Date.prototype.toTimeString()`](totimestring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toString>

