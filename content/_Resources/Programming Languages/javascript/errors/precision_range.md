RangeError: precision is out of range
=====================================

 
The JavaScript exception \"precision is out of range\" occurs when a
number that\'s outside of the range of 0 and 20 (or 21) was passed into
`toFixed` or `toPrecision`.


 
Message
-------

 
```text
RangeError: toExponential() argument must be between 0 and 100 (V8-based & Safari)
RangeError: toFixed() digits argument must be between 0 and 100 (V8-based & Safari)
RangeError: toPrecision() argument must be between 1 and 100 (V8-based & Safari)
RangeError: precision -1 out of range (Firefox)
```



 
Error type 
----------

 
[`RangeError`](../global_objects/rangeerror)



 
What went wrong? 
----------------

 
There was an out of range precision argument in one of these methods:

-   [`Number.prototype.toExponential()`](../global_objects/number/toexponential),
    which requires the arguments to be between 0 and 100, inclusive.
-   [`Number.prototype.toFixed()`](../global_objects/number/tofixed),
    which requires the arguments to be between 0 and 100, inclusive.
-   [`Number.prototype.toPrecision()`](../global_objects/number/toprecision),
    which requires the arguments to be between 1 and 100, inclusive.



 
Examples
--------


 
### Invalid cases 

 
 
 
[js]


```js
(77.1234).toExponential(-1); // RangeError
(77.1234).toExponential(101); // RangeError

(2.34).toFixed(-100); // RangeError
(2.34).toFixed(1001); // RangeError

(1234.5).toPrecision(-1); // RangeError
(1234.5).toPrecision(101); // RangeError
```




 
### Valid cases 

 
 
 
[js]


```js
(77.1234).toExponential(4); // 7.7123e+1
(77.1234).toExponential(2); // 7.71e+1

(2.34).toFixed(1); // 2.3
(2.35).toFixed(1); // 2.4 (note that it rounds up in this case)

(5.123456).toPrecision(5); // 5.1235
(5.123456).toPrecision(2); // 5.1
(5.123456).toPrecision(1); // 5
```




 
See also 
--------

 
-   [`Number.prototype.toExponential()`](../global_objects/number/toexponential)
-   [`Number.prototype.toFixed()`](../global_objects/number/tofixed)
-   [`Number.prototype.toPrecision()`](../global_objects/number/toprecision)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Precision_range>

