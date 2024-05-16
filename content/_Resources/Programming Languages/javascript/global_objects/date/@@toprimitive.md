Date.prototype\[@\@toPrimitive\]()
==================================

 
The `[@@toPrimitive]()` method of [`Date`](../date) instances returns a
primitive value representing this date. It may either be a string or a
number, depending on the hint given.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
date[Symbol.toPrimitive](hint)
```




 
### Parameters

 

[`hint`](#hint)

:   A string representing the type of the primitive value to return. The
    following values are valid:

    -   `"string"` or `"default"`: The method should return a string.
    -   `"number"`: The method should return a number.



 
### Return value 

 
If `hint` is `"string"` or `"default"`, this method returns a string by
[coercing the `this` value to a string](../string#string_coercion)
(first trying `toString()` then trying `valueOf()`).

If `hint` is `"number"`, this method returns a number by [coercing the
`this` value to a number](../number#number_coercion) (first trying
`valueOf()` then trying `toString()`).



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if the `hint` argument is not one of the three valid values.



 
Description
-----------

 
The `[@@toPrimitive]()` method is part of the [type coercion
protocol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#type_coercion).
JavaScript always calls the `[@@toPrimitive]()` method in priority to
convert an object to a primitive value. You rarely need to invoke the
`[@@toPrimitive]()` method yourself; JavaScript automatically invokes it
when encountering an object where a primitive value is expected.

The `[@@toPrimitive]()` method of the [`Date`](../date) object returns a
primitive value by either invoking [`this.valueOf()`](valueof) and
returning a number, or invoking [`this.toString()`](tostring) and
returning a string. It exists to override the default [primitive
coercion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#primitive_coercion)
process to return a string instead of a number, because primitive
coercion, by default, calls [`valueOf()`](valueof) before
[`toString()`](tostring). With the custom `[@@toPrimitive]()`,
`new Date(0) + 1` returns
`"Thu Jan 01 1970 00:00:00 GMT+0000 (Coordinated Universal Time)1"` (a
string) instead of `1` (a number).



 
Examples
--------


 
### Using \[@\@toPrimitive\]() 

 
 
 
[js]


```js
const d = new Date(0); // 1970-01-01T00:00:00.000Z

d[Symbol.toPrimitive]("string"); // "Thu Jan 01 1970 00:00:00 GMT+0000 (Coordinated Universal Time)"
d[Symbol.toPrimitive]("number"); // 0
d[Symbol.toPrimitive]("default"); // "Thu Jan 01 1970 00:00:00 GMT+0000 (Coordinated Universal Time)"
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype-@\@toprimitive]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype-@@toprimitive)

  ----------------------------------------------------------------------------------------------------------------------------------------


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

`@@toPrimitive`

47

15

44

34

10

47

44

34

10

5.0

47

1.0

6.0.0

 
See also 
--------

 
-   [`Symbol.toPrimitive`](../symbol/toprimitive)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/@@toPrimitive>

