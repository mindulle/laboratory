Date.prototype.setUTCMilliseconds()
===================================

 
The `setUTCMilliseconds()` method of [`Date`](../date) instances changes
the milliseconds for this date according to universal time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
setUTCMilliseconds(millisecondsValue)
```




 
### Parameters

 

[`millisecondsValue`](#millisecondsvalue)

:   An integer between 0 and 999 representing the milliseconds.



 
### Return value 

 
Changes the [`Date`](../date) object in place, and returns its new
[timestamp](../date#the_epoch_timestamps_and_invalid_date). If
`millisecondsValue` is `NaN` (or other values that get
[coerced](../number#number_coercion) to `NaN`, such as `undefined`), the
date is set to [Invalid
Date](../date#the_epoch_timestamps_and_invalid_date) and `NaN` is
returned.



 
Description
-----------

 
If a parameter you specify is outside of the expected range,
`setUTCMilliseconds()` attempts to update the date information in the
[`Date`](../date) object accordingly. For example, if you use 1100 for
`millisecondsValue`, the seconds stored in the [`Date`](../date) object
will be incremented by 1, and 100 will be used for milliseconds.



 
Examples
--------


 
### Using setUTCMilliseconds() 

 
 
 
[js]


```js
const theBigDay = new Date();
theBigDay.setUTCMilliseconds(500);
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.setutcmilliseconds]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.setutcmilliseconds)

  -------------------------------------------------------------------------------------------------------------------------------------------------


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

`setUTCMilliseconds`

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

 
-   [`Date.prototype.getUTCMilliseconds()`](getutcmilliseconds)
-   [`Date.prototype.setMilliseconds()`](setmilliseconds)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setUTCMilliseconds>

