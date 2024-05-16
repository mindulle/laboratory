Date.prototype.getUTCHours()
============================

 
The `getUTCHours()` method of [`Date`](../date) instances returns the
hours for this date according to universal time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
getUTCHours()
```




 
### Parameters

 
None.



 
### Return value 

 
An integer, between 0 and 23, representing the hours for the given date
according to universal time. Returns `NaN` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Examples
--------


 
### Using getUTCHours() 

 
The following example assigns the hours portion of the current time to
the variable `hours`.

 
 
[js]


```js
const today = new Date();
const hours = today.getUTCHours();
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.getutchours]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.getutchours)

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

`getUTCHours`

1

12

1

4

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

 
-   [`Date.prototype.getHours()`](gethours)
-   [`Date.prototype.setUTCHours()`](setutchours)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getUTCHours>

