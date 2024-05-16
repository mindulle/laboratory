Number.parseFloat()
===================

 
The `Number.parseFloat()` static method parses an argument and returns a
floating point number. If a number cannot be parsed from the argument,
it returns [`NaN`](../nan).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Number.parseFloat(string)
```




 
### Parameters

 

[`string`](#string)

:   The value to parse, [coerced to a
    string](../string#string_coercion). Leading
    [whitespace](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace)
    in this argument is ignored.



 
### Return value 

 
A floating point number parsed from the given `string`.

Or [`NaN`](../nan) when the first non-whitespace character cannot be
converted to a number.



 
Examples
--------


 
### Number.parseFloat vs. parseFloat 

 
This method has the same functionality as the global
[`parseFloat()`](../parsefloat) function:

 
 
[js]


```js
Number.parseFloat === parseFloat; // true
```


Its purpose is modularization of globals.

See [`parseFloat()`](../parsefloat) for more detail and examples.



Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.parsefloat]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.parsefloat)

  -----------------------------------------------------------------------------------------------------------------


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

`parseFloat`

34

12

25

21

9

34

25

21

9

2.0

37

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `Number.parseFloat` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-number)
-   [`Number`](../number)
-   [`parseFloat()`](../parsefloat)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/parseFloat>

