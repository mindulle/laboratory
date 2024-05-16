Intl.NumberFormat.prototype.format()
====================================

 
The `format()` method of [`Intl.NumberFormat`](../numberformat)
instances formats a number according to the [locale and formatting
options](numberformat#parameters) of this `Intl.NumberFormat` object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
format(number)
```




 
### Parameters

 

[`number`](#number)

:   A [`Number`](../../number), [`BigInt`](../../bigint), or string, to
    format. Strings are parsed in the same way as in [number
    conversion](../../number#number_coercion), except that `format()`
    will use the exact value that the string represents, avoiding loss
    of precision during implicitly conversion to a number.

 
**Note:** Older versions of the specification parsed strings as a
[`Number`](../../number). Check the compatibility table for your
browser.




 
### Return value 

 
A string representing the given `number` formatted according to the
locale and formatting options of this
[`Intl.NumberFormat`](../numberformat) object.



 
Description
-----------

 
[`Number`](../../number) values in JavaScript suffer from loss of
precision if they are too big or too small, making the text
representation inaccurate. If you are performing calculations with
integers larger than
[`Number.MAX_SAFE_INTEGER`](../../number/max_safe_integer) you should
use a [`BigInt`](../../bigint) instead, which will format correctly:

 
 
[js]


```js
new Intl.NumberFormat("en-US").format(1234567891234567891); // 1,234,567,891,234,568,000
new Intl.NumberFormat("en-US").format(1234567891234567891n); // 1,234,567,891,234,567,891
```


You can also pass through very large strings to be formatted as an
arbitrary-precision decimal string (if you\'re performing calculations
on the data you will still need to work with `BigInt`):

 
 
[js]


```js
new Intl.NumberFormat("en-US").format("1234567891234567891"); // 1,234,567,891,234,567,891
```




 
Examples
--------


 
### Using format 

 
Use the `format` getter function for formatting a single currency value.
The code below shows how to format the roubles currency for a Russian
locale:

 
 
[js]


```js
const options = { style: "currency", currency: "RUB" };
const numberFormat = new Intl.NumberFormat("ru-RU", options);
console.log(numberFormat.format(654321.987));
// "654 321,99 ₽"
```




 
### Using format with map 

 
Use the `format` getter function for formatting all numbers in an array.
Note that the function is bound to the
[`Intl.NumberFormat`](../numberformat) from which it was obtained, so it
can be passed directly to [`Array.prototype.map`](../../array/map). This
is considered a historical artefact, as part of a convention which is no
longer followed for new features, but is preserved to maintain
compatibility with existing programs.

 
 
[js]


```js
const a = [123456.789, 987654.321, 456789.123];
const numberFormat = new Intl.NumberFormat("es-ES");
const formatted = a.map((n) => numberFormat.format(n));
console.log(formatted.join("; "));
// "123.456,789; 987.654,321; 456.789,123"
```




 
### Using format with a string 

 
Using a string we can specify very numbers that are larger than
[`Number.MAX_SAFE_INTEGER`](../../number/max_safe_integer) without
losing precision.

 
 
[js]


```js
const numberFormat = new Intl.NumberFormat("en-US");

// Here the value is converted to a Number
console.log(numberFormat.format(987654321987654321));
// 987,654,321,987,654,300

// Here we use a string and don't lose precision
console.log(numberFormat.format("987654321987654321"));
// 987,654,321,987,654,321
```


We can also use the general \"E\" exponent syntax for decimal strings:
`#.#E#`. The code below creates a [`BigInt`](../../bigint), coerces it
to a string with the suffix `E-6`, and then formats it.

 
 
[js]


```js
const numberFormat = new Intl.NumberFormat("en-US");
const bigNum = 1000000000000000110000n;
console.log(numberFormat.format(bigNum));
// "1,000,000,000,000,000,110,000"

// Format as a string using the `E` syntax:
console.log(numberFormat.format(`${bigNum}E-6`));
// "1,000,000,000,000,000.11"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.numberformat.prototype.format]](https://tc39.es/ecma402/#sec-intl.numberformat.prototype.format)

  -------------------------------------------------------------------------------------------------------------------


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

`format`

24

12Before Edge 18, numbers are rounded to 15 decimal digits. For example,
`new Intl.NumberFormat('en-US').format(1000000000000005)` returns
`"1,000,000,000,000,010"`.

29

15

10

25

56

14

10

1.5

4.4

1.8

0.12.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `NumberFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/NumberFormat)
for more details.

`number_parameter-string_decimal`

106

106

116

92

15.4

106

116

72

15.4

20.0

106

No

19.0.0

 
See also 
--------

 
-   [`Intl.NumberFormat`](../numberformat)
-   [`Number.prototype.toLocaleString()`](../../number/tolocalestring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/format>

