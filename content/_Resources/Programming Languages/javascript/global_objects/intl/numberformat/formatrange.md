Intl.NumberFormat.prototype.formatRange()
=========================================

 
The `formatRange()` method of [`Intl.NumberFormat`](../numberformat)
instances formats a range of numbers according to the locale and
formatting options of this `Intl.NumberFormat` object.


 
Syntax
------

 
 
 
[js]


```js
formatRange(startRange, endRange)
```




 
### Parameters

 

[`startRange`](#startrange)

:   A [`Number`](../../number) or [`BigInt`](../../bigint).

[`endRange`](#endrange)

:   A [`Number`](../../number) or [`BigInt`](../../bigint).



 
### Return value 

 
A string representing the given range of numbers formatted according to
the locale and formatting options of this
[`Intl.NumberFormat`](../numberformat) object.



 
### Exceptions

 

[`RangeError`](../../rangeerror)

:   Thrown if `startRange` is less than `endRange`, or either value is
    `NaN`.

[`TypeError`](../../typeerror)

:   Thrown if either `startRange` or `endRange` is undefined.



 
Description
-----------

 
The `formatRange` getter function formats a range of numbers into a
string according to the locale and formatting options of this
[`Intl.NumberFormat`](../numberformat) object from which it is called.



 
Examples
--------


 
### Using formatRange 

 
Use the `formatRange` getter function for formatting a range of currency
values:

 
 
[js]


```js
const nf = new Intl.NumberFormat("en-US", {
  style: "currency",
  currency: "USD",
  maximumFractionDigits: 0,
});

console.log(nf.formatRange(3, 5)); // "$3 – $5"

// Note: the "approximately equals" symbol is added if
// startRange and endRange round to the same values.
console.log(nf.formatRange(2.9, 3.1)); // "~$3"
```


 
 
[js]


```js
const nf = new Intl.NumberFormat("es-ES", {
  style: "currency",
  currency: "EUR",
  maximumFractionDigits: 0,
});

console.log(nf.formatRange(3, 5)); // "3-5 €"
console.log(nf.formatRange(2.9, 3.1)); // "~3 €"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.numberformat.prototype.formatrange]](https://tc39.es/ecma402/#sec-intl.numberformat.prototype.formatrange)

  -----------------------------------------------------------------------------------------------------------------------------


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

`formatRange`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat/formatRange>

