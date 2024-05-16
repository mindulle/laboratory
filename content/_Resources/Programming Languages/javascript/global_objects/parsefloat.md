parseFloat()
============

 
The `parseFloat()` function parses a string argument and returns a
floating point number.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
parseFloat(string)
```




 
### Parameters

 

[`string`](#string)

:   The value to parse, [coerced to a string](string#string_coercion).
    Leading
    [whitespace](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace)
    in this argument is ignored.



 
### Return value 

 
A floating point number parsed from the given `string`, or [`NaN`](nan)
when the first non-whitespace character cannot be converted to a number.

 
**Note:** JavaScript does not have the distinction of \"floating point
numbers\" and \"integers\" on the language level.
[`parseInt()`](parseint) and `parseFloat()` only differ in their parsing
behavior, but not necessarily their return values. For example,
`parseInt("42")` and `parseFloat("42")` would return the same value: a
[`Number`](number) 42.




 
Description
-----------

 
The `parseFloat` function converts its first argument to a string,
parses that string as a decimal number literal, then returns a number or
`NaN`. The number syntax it accepts can be summarized as:

-   The characters accepted by `parseFloat()` are plus sign (`+`), minus
    sign (`-` U+002D HYPHEN-MINUS), decimal digits (`0` -- `9`), decimal
    point (`.`), exponent indicator (`e` or `E`), and the `"Infinity"`
    literal.
-   The `+`/`-` signs can only appear strictly at the beginning of the
    string, or immediately following the `e`/`E` character. The decimal
    point can only appear once, and only before the `e`/`E` character.
    The `e`/`E` character can only appear once, and only if there is at
    least one digit before it.
-   Leading spaces in the argument are trimmed and ignored.
-   `parseFloat()` can also parse and return [`Infinity`](infinity) or
    `-Infinity` if the string starts with `"Infinity"` or `"-Infinity"`
    preceded by none or more white spaces.
-   `parseFloat()` picks the longest substring starting from the
    beginning that generates a valid number literal. If it encounters an
    invalid character, it returns the number represented up to that
    point, ignoring the invalid character and all characters following
    it.
-   If the argument\'s first character can\'t start a legal number
    literal per the syntax above, `parseFloat` returns [`NaN`](nan).

Syntax-wise, `parseFloat()` parses a subset of the syntax that the
[`Number()`](number/number) function accepts. Namely, `parseFloat()`
does not support non-decimal literals with `0x`, `0b`, or `0o` prefixes
but supports everything else. However, `parseFloat()` is more lenient
than `Number()` because it ignores trailing invalid characters, which
would cause `Number()` to return `NaN`.

Similar to number literals and `Number()`, the number returned from
`parseFloat()` may not be exactly equal to the number represented by the
string, due to floating point range and inaccuracy. For numbers outside
the `-1.7976931348623158e+308` -- `1.7976931348623158e+308` range (see
[`Number.MAX_VALUE`](number/max_value)), `-Infinity` or `Infinity` is
returned.



 
Examples
--------


 
### Using parseFloat() 

 
The following examples all return `3.14`:

 
 
[js]


```js
parseFloat(3.14);
parseFloat("3.14");
parseFloat("  3.14  ");
parseFloat("314e-2");
parseFloat("0.0314E+2");
parseFloat("3.14some non-digit characters");
parseFloat({
  toString() {
    return "3.14";
  },
});
```




 
### parseFloat() returning NaN 

 
The following example returns `NaN`:

 
 
[js]


```js
parseFloat("FF2");
```


Anecdotally, because the string `NaN` itself is invalid syntax as
accepted by `parseFloat()`, passing `"NaN"` returns `NaN` as well.

 
 
[js]


```js
parseFloat("NaN"); // NaN
```




 
### Returning Infinity 

 
Infinity values are returned when the number is outside the
double-precision 64-bit IEEE 754-2019 format range:

 
 
[js]


```js
parseFloat("1.7976931348623159e+308"); // Infinity
parseFloat("-1.7976931348623159e+308"); // -Infinity
```


Infinity is also returned when the string starts with `"Infinity"` or
`"-Infinity"`:

 
 
[js]


```js
parseFloat("Infinity"); // Infinity
parseFloat("-Infinity"); // -Infinity
```




 
### Interaction with BigInt values 

 
`parseFloat()` does not handle [`BigInt`](bigint) values. It stops at
the `n` character, and treats the preceding string as a normal integer,
with possible loss of precision. If a BigInt value is passed to
`parseFloat()`, it will be converted to a string, and the string will be
parsed as a floating-point number, which may result in loss of precision
as well.

 
 
[js]


```js
parseFloat(900719925474099267n); // 900719925474099300
parseFloat("900719925474099267n"); // 900719925474099300
```


You should pass the string to the [`BigInt()`](bigint/bigint) function
instead, without the trailing `n` character.

 
 
[js]


```js
BigInt("900719925474099267");
// 900719925474099267n
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-parsefloat-string]](https://tc39.es/ecma262/multipage/global-object.html#sec-parsefloat-string)

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

`parseFloat`

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

 
-   [`parseInt()`](parseint)
-   [`Number.parseFloat()`](number/parsefloat)
-   [`Number.parseInt()`](number/parseint)
-   [`Number.prototype.toFixed()`](number/tofixed)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat>

