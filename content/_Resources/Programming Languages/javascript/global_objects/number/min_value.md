Number.MIN\_VALUE
=================

 
The `Number.MIN_VALUE` static data property represents the smallest
positive numeric value representable in JavaScript.


 
Try it 
------

 



 
Value
-----

 
2^-1074^, or `5E-324`.

 
Property attributes of `Number.MIN_VALUE`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
`Number.MIN_VALUE` is the smallest positive number (not the most
negative number) that can be represented within float precision --- in
other words, the number closest to 0. The ECMAScript spec doesn\'t
define a precise value that implementations are required to support ---
instead the spec says, *\"must be the smallest non-zero positive value
that can actually be represented by the implementation\"*. This is
because small IEEE-754 floating point numbers are
[denormalized](https://en.wikipedia.org/wiki/Subnormal_number), but
implementations are not required to support this representation, in
which case `Number.MIN_VALUE` may be larger.

In practice, its precise value in mainstream engines like V8 (used by
Chrome, Edge, Node.js), SpiderMonkey (used by Firefox), and
JavaScriptCore (used by Safari) is 2^-1074^, or `5E-324`.

Because `MIN_VALUE` is a static property of [`Number`](../number), you
always use it as `Number.MIN_VALUE`, rather than as a property of a
number value.



 
Examples
--------


 
### Using MIN\_VALUE 

 
The following code divides two numeric values. If the result is greater
than or equal to `MIN_VALUE`, the `func1` function is called; otherwise,
the `func2` function is called.

 
 
[js]


```js
if (num1 / num2 >= Number.MIN_VALUE) {
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
  sec-number.min\_value]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.min_value)

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

`MIN_VALUE`

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

 
-   [`Number.MAX_VALUE`](max_value)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/MIN_VALUE>

