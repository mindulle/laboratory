Date.prototype.valueOf()
========================

 
The `valueOf()` method of [`Date`](../date) instances returns the number
of milliseconds for this date since the
[epoch](../date#the_epoch_timestamps_and_invalid_date), which is defined
as the midnight at the beginning of January 1, 1970, UTC.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
valueOf()
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

 
The `valueOf()` method is part of the [type coercion
protocol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#type_coercion).
Because `Date` has a [`[@@toPrimitive]()`](@@toprimitive) method, that
method always takes priority over `valueOf()` when a `Date` object is
implicitly [coerced to a number](../number#number_coercion). However,
`Date.prototype[@@toPrimitive]()` still calls `this.valueOf()`
internally.

The [`Date`](../date) object overrides the
[`valueOf()`](../object/valueof) method of [`Object`](../object).
`Date.prototype.valueOf()` returns the timestamp of the date, which is
functionally equivalent to the [`Date.prototype.getTime()`](gettime)
method.



 
Examples
--------


 
### Using valueOf() 

 
 
 
[js]


```js
const d = new Date(0); // 1970-01-01T00:00:00.000Z
console.log(d.valueOf()); // 0
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.valueof]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.valueof)

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

`valueOf`

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

 
-   [`Object.prototype.valueOf()`](../object/valueof)
-   [`Date.prototype.getTime()`](gettime)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/valueOf>

