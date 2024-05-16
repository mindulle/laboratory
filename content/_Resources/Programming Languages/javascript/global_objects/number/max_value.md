Number.MAX\_VALUE
=================

 
The `Number.MAX_VALUE` static data property represents the maximum
numeric value representable in JavaScript.


 
Try it 
------

 



 
Value
-----

 
2^1024^ - 2^971^, or approximately `1.7976931348623157E+308`.

 
Property attributes of `Number.MAX_VALUE`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
Values larger than `MAX_VALUE` are represented as
[`Infinity`](../infinity) and will lose their actual value.

Because `MAX_VALUE` is a static property of [`Number`](../number), you
always use it as `Number.MAX_VALUE`, rather than as a property of a
number value.



 
Examples
--------


 
### Using MAX\_VALUE 

 
The following code multiplies two numeric values. If the result is less
than or equal to `MAX_VALUE`, the `func1` function is called; otherwise,
the `func2` function is called.

 
 
[js]


```js
if (num1 * num2 <= Number.MAX_VALUE) {
  func1();
} else {
  func2();
}
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.max\_value]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.max_value)

  ----------------------------------------------------------------------------------------------------------------


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

`MAX_VALUE`

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

 
-   [`Number.MIN_VALUE`](min_value)
-   [`Number`](../number)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/MAX_VALUE>

