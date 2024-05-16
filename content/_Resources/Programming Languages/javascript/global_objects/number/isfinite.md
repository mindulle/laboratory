Number.isFinite()
=================

 
The `Number.isFinite()` static method determines whether the passed
value is a finite number --- that is, it checks that a given value is a
number, and the number is neither positive [`Infinity`](../infinity),
negative `Infinity`, nor [`NaN`](../nan).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Number.isFinite(value)
```




 
### Parameters

 

[`value`](#value)

:   The value to be tested for finiteness.



 
### Return value 

 
The boolean value `true` if the given value is a finite number.
Otherwise `false`.



 
Examples
--------


 
### Using isFinite() 

 
 
 
[js]


```js
Number.isFinite(Infinity); // false
Number.isFinite(NaN); // false
Number.isFinite(-Infinity); // false

Number.isFinite(0); // true
Number.isFinite(2e64); // true
```




 
### Difference between Number.isFinite() and global isFinite() 

 
In comparison to the global [`isFinite()`](../isfinite) function, this
method doesn\'t first convert the parameter to a number. This means only
values of the type number *and* are finite return `true`, and
non-numbers always return `false`.

 
 
[js]


```js
isFinite("0"); // true; coerced to number 0
Number.isFinite("0"); // false
isFinite(null); // true; coerced to number 0
Number.isFinite(null); // false
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.isfinite]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.isfinite)

  -------------------------------------------------------------------------------------------------------------


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

19

12

16

15

9

25

16

14

9

1.5

4.4

1.0

0.10.0

 
See also 
--------

 
-   [Polyfill of `Number.isFinite` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-number)
-   [`Number`](../number)
-   [`isFinite()`](../isfinite)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isFinite>

