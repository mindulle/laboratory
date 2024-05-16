Number.parseInt()
=================

 
The `Number.parseInt()` static method parses a string argument and
returns an integer of the specified radix or base.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Number.parseInt(string)
Number.parseInt(string, radix)
```




 
### Parameters

 

[`string`](#string)

:   The value to parse, [coerced to a
    string](../string#string_coercion). Leading whitespace in this
    argument is ignored.

[`radix`](#radix) [Optional]

:   An integer between `2` and `36` that represents the *radix* (the
    base in mathematical numeral systems) of the `string`.

    If `radix` is undefined or `0`, it is assumed to be `10` except when
    the number begins with the code unit pairs `0x` or `0X`, in which
    case a radix of `16` is assumed.



 
### Return value 

 
An integer parsed from the given `string`.

If the `radix` is smaller than `2` or bigger than `36`, or the first
non-whitespace character cannot be converted to a number,
[`NaN`](../nan) is returned.



 
Examples
--------


 
### Number.parseInt vs. parseInt 

 
This method has the same functionality as the global
[`parseInt()`](../parseint) function:

 
 
[js]


```js
Number.parseInt === parseInt; // true
```


Its purpose is modularization of globals. Please see
[`parseInt()`](../parseint) for more detail and examples.



Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.parseint]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.parseint)

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

`parseInt`

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

 
-   [Polyfill of `Number.parseInt` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-number)
-   [`Number`](../number)
-   [`parseInt()`](../parseint)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/parseInt>

