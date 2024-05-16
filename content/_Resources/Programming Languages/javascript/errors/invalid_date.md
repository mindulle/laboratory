RangeError: invalid date
========================

 
The JavaScript exception \"invalid date\" occurs when a string leading
to an invalid date has been provided to [`Date`](../global_objects/date)
or [`Date.parse()`](../global_objects/date/parse).


 
Message
-------

 
```text
RangeError: Invalid time value (V8-based)
RangeError: invalid date (Firefox)
RangeError: Invalid Date (Safari)
```



 
Error type 
----------

 
[`RangeError`](../global_objects/rangeerror)



 
What went wrong? 
----------------

 
A string leading to an invalid date has been provided to
[`Date`](../global_objects/date) or
[`Date.parse()`](../global_objects/date/parse).



 
Examples
--------


 
### Invalid cases 

 
Unrecognizable strings or dates containing illegal element values in ISO
formatted strings usually return [`NaN`](../global_objects/nan).
However, depending on the implementation, non--conforming ISO format
strings, may also throw `RangeError: invalid date`, like the following
cases in Firefox:

 
 
[js]


```js
new Date("foo-bar 2014");
new Date("2014-25-23").toISOString();
new Date("foo-bar 2014").toString();
```


This, however, returns [`NaN`](../global_objects/nan) in Firefox:

 
 
[js]


```js
Date.parse("foo-bar 2014"); // NaN
```


For more details, see the [`Date.parse()`](../global_objects/date/parse)
documentation.



 
### Valid cases 

 
 
 
[js]


```js
new Date("05 October 2011 14:48 UTC");
new Date(1317826080); // Unix Timestamp for 05 October 2011 14:48:00 UTC
```




 
See also 
--------

 
-   [`Date`](../global_objects/date)
-   [`Date.prototype.parse()`](../global_objects/date/parse)
-   [`Date.prototype.toISOString()`](../global_objects/date/toisostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_date>

