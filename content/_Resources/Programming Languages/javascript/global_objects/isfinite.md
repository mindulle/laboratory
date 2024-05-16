isFinite()
==========

 
The `isFinite()` function determines whether a value is finite, first
converting the value to a number if necessary. A finite number is one
that\'s not [`NaN`](nan) or ±[`Infinity`](infinity). Because coercion
inside the `isFinite()` function can be [surprising](isnan#description),
you may prefer to use [`Number.isFinite()`](number/isfinite).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
isFinite(value)
```




 
### Parameters

 

[`value`](#value)

:   The value to be tested.



 
### Return value 

 
`false` if the given value is [`NaN`](nan), [`Infinity`](infinity), or
`-Infinity` after being [converted to a number](number#number_coercion);
otherwise, `true`.



 
Description
-----------

 
`isFinite()` is a function property of the global object.

When the argument to the `isFinite()` function is not of type
[Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#number_type),
the value is first coerced to a number, and the resulting value is then
compared against `NaN` and ±Infinity. This is as confusing as the
behavior of [`isNaN`](isnan) --- for example, `isFinite("1")` is `true`.

[`Number.isFinite()`](number/isfinite) is a more reliable way to test
whether a value is a finite number value, because it returns `false` for
any non-number input.



 
Examples
--------


 
### Using isFinite() 

 
 
 
[js]


```js
isFinite(Infinity); // false
isFinite(NaN); // false
isFinite(-Infinity); // false

isFinite(0); // true
isFinite(2e64); // true
isFinite(910); // true

// Would've been false with the more robust Number.isFinite():
isFinite(null); // true
isFinite("0"); // true
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-isfinite-number]](https://tc39.es/ecma262/multipage/global-object.html#sec-isfinite-number)

  ---------------------------------------------------------------------------------------------------------


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

`isFinite`

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

 
-   [`Number.isFinite()`](number/isfinite)
-   [`Number.NaN`](number/nan)
-   [`Number.POSITIVE_INFINITY`](number/positive_infinity)
-   [`Number.NEGATIVE_INFINITY`](number/negative_infinity)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isFinite>

