Date.prototype.getTime()
========================

 
The `getTime()` method of [`Date`](../date) instances returns the number
of milliseconds for this date since the
[epoch](../date#the_epoch_timestamps_and_invalid_date), which is defined
as the midnight at the beginning of January 1, 1970, UTC.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
getTime()
```




 
### Parameters

 
None.



 
### Return value 

 
A number representing the
[timestamp](../date#the_epoch_timestamps_and_invalid_date), in
milliseconds, of this date. Returns `NaN` if the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date).



 
Description
-----------

 
`Date` objects are fundamentally represented by a
[timestamp](../date#the_epoch_timestamps_and_invalid_date), and this
method allows you to retrieve the timestamp. You can use this method to
help assign a date and time to another [`Date`](../date) object. This
method is functionally equivalent to the [`valueOf()`](valueof) method.



 
### Reduced time precision 

 
To offer protection against timing attacks and
[fingerprinting](https://developer.mozilla.org/en-US/docs/Glossary/Fingerprinting),
the precision of `new Date().getTime()` might get rounded depending on
browser settings. In Firefox, the `privacy.reduceTimerPrecision`
preference is enabled by default and defaults to 2ms. You can also
enable `privacy.resistFingerprinting`, in which case the precision will
be 100ms or the value of
`privacy.resistFingerprinting.reduceTimerPrecision.microseconds`,
whichever is larger.

 
 
[js]


```js
// reduced time precision (2ms) in Firefox 60
new Date().getTime();
// 1519211809934
// 1519211810362
// 1519211811670
// …

// reduced time precision with `privacy.resistFingerprinting` enabled
new Date().getTime();
// 1519129853500
// 1519129858900
// 1519129864400
// …
```




 
Examples
--------


 
### Using getTime() for copying dates 

 
Constructing a date object with the identical time value.

 
 
[js]


```js
// Since month is zero based, birthday will be January 10, 1995
const birthday = new Date(1994, 12, 10);
const copy = new Date();
copy.setTime(birthday.getTime());
```




 
### Measuring execution time 

 
Subtracting two subsequent `getTime()` calls on newly generated
[`Date`](../date) objects, give the time span between these two calls.
This can be used to calculate the executing time of some operations. See
also [`Date.now()`](now) to prevent instantiating unnecessary
[`Date`](../date) objects.

 
 
[js]


```js
let end, start;

start = new Date();
for (let i = 0; i < 1000; i++) {
  Math.sqrt(i);
}
end = new Date();

console.log(`Operation took ${end.getTime() - start.getTime()} msec`);
```


 
**Note:** In browsers that support the [Web Performance
API](https://developer.mozilla.org/en-US/docs/Web/API/performance_property)\'s
high-resolution time feature,
[`Performance.now()`](https://developer.mozilla.org/en-US/docs/Web/API/Performance/now)
can provide more reliable and precise measurements of elapsed time than
[`Date.now()`](now).




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.gettime]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.gettime)

  ---------------------------------------------------------------------------------------------------------------------------


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

`getTime`

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

 
-   [`Date.prototype.setTime()`](settime)
-   [`Date.prototype.valueOf()`](valueof)
-   [`Date.now()`](now)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getTime>

