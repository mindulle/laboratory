Date.now()
==========

 
The `Date.now()` static method returns the number of milliseconds
elapsed since the
[epoch](../date#the_epoch_timestamps_and_invalid_date), which is defined
as the midnight at the beginning of January 1, 1970, UTC.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Date.now()
```




 
### Parameters

 
None.



 
### Return value 

 
A number representing the
[timestamp](../date#the_epoch_timestamps_and_invalid_date), in
milliseconds, of the current time.



 
Description
-----------


 
### Reduced time precision 

 
To offer protection against timing attacks and
[fingerprinting](https://developer.mozilla.org/en-US/docs/Glossary/Fingerprinting),
the precision of `Date.now()` might get rounded depending on browser
settings. In Firefox, the `privacy.reduceTimerPrecision` preference is
enabled by default and defaults to 2ms. You can also enable
`privacy.resistFingerprinting`, in which case the precision will be
100ms or the value of
`privacy.resistFingerprinting.reduceTimerPrecision.microseconds`,
whichever is larger.

 
 
[js]


```js
// reduced time precision (2ms) in Firefox 60
Date.now();
// 1519211809934
// 1519211810362
// 1519211811670
// …

// reduced time precision with `privacy.resistFingerprinting` enabled
Date.now();
// 1519129853500
// 1519129858900
// 1519129864400
// …
```




 
Examples
--------


 
### Measuring time elapsed 

 
You can use `Date.now()` to get the current time in milliseconds, then
subtract a previous time to find out how much time elapsed between the
two calls.

 
 
[js]


```js
const start = Date.now();
doSomeLongRunningProcess();
console.log(`Time elapsed: ${Date.now() - start} ms`);
```


For more complex scenarios, you may want to use the [performance
API](https://developer.mozilla.org/en-US/docs/Web/API/Performance_API/High_precision_timing)
instead.



Specifications
--------------

 
  -----------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.now]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.now)

  -----------------------------------------------------------------------------------------------


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

`now`

1

12

1

10.5

4

18

4

14

4

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [Polyfill of `Date.now` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-date)
-   [`Performance.now()`](https://developer.mozilla.org/en-US/docs/Web/API/Performance/now)
-   [`console.time()`](https://developer.mozilla.org/en-US/docs/Web/API/console/time_static)
-   [`console.timeEnd()`](https://developer.mozilla.org/en-US/docs/Web/API/console/timeend_static)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/now>

