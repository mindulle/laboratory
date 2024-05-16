Date.prototype.getMilliseconds()
================================

 
The `getMilliseconds()` method of [`Date`](../date) instances returns
the milliseconds for this date according to local time.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
getMilliseconds()
```




 
### Parameters

 
None.



 
### Return value 

 
An integer, between 0 and 999, representing the milliseconds for the
given date according to local time. Returns `NaN` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Examples
--------


 
### Using getMilliseconds() 

 
The `milliseconds` variable has value `0`, based on the value of the
[`Date`](../date) object `xmas95`, which doesn\'t specify the
milliseconds component, so it defaults to 0.

 
 
[js]


```js
const xmas95 = new Date("1995-12-25T23:15:30");
const milliseconds = xmas95.getMilliseconds();

console.log(milliseconds); // 0
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.getmilliseconds]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.getmilliseconds)

  -------------------------------------------------------------------------------------------------------------------------------------------


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

`getMilliseconds`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getMilliseconds>

