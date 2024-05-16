Number.NaN
==========

 
The `Number.NaN` static data property represents Not-A-Number, which is
equivalent to [`NaN`](../nan). For more information about the behaviors
of `NaN`, see the [description for the global property](../nan).


 
Try it 
------

 



 
Value
-----

 
The number value [`NaN`](../nan).

 
Property attributes of `Number.NaN`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
Because `NaN` is a static property of [`Number`](../number), you always
use it as `Number.NaN`, rather than as a property of a number value.



 
Examples
--------


 
### Checking whether values are numeric 

 
 
 
[js]


```js
function sanitize(x) {
  if (isNaN(x)) {
    return Number.NaN;
  }
  return x;
}
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.nan]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.nan)

  ---------------------------------------------------------------------------------------------------


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

`NaN`

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

 
-   [`NaN`](../nan)
-   [`Number.isNaN()`](isnan)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/NaN>

