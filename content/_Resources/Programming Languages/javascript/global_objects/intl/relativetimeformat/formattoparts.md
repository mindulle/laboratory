Intl.RelativeTimeFormat.prototype.formatToParts()
=================================================

 
The `formatToParts()` method of
[`Intl.RelativeTimeFormat`](../relativetimeformat) instances returns an
[`Array`](../../array) of objects representing the relative time format
in parts that can be used for custom locale-aware formatting.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
formatToParts(value, unit)
```




 
### Parameters

 

[`value`](#value)

:   Numeric value to use in the internationalized relative time message.

[`unit`](#unit)

:   Unit to use in the relative time internationalized message. Possible
    values are: `"year"`, `"quarter"`, `"month"`, `"week"`, `"day"`,
    `"hour"`, `"minute"`, `"second"`. Plural forms are also permitted.



 
### Return value 

 
An [`Array`](../../array) of objects containing the formatted relative
time in parts.



 
Description
-----------

 
The `Intl.RelativeTimeFormat.prototype.formatToParts` method is a
version of the format method which it returns an array of objects which
represent \"parts\" of the object, separating the formatted number into
its constituent parts and separating it from other surrounding text.
These objects have two properties: type a `NumberFormat` formatToParts
type, and value, which is the String which is the component of the
output. If a \"part\" came from `NumberFormat`, it will have a unit
property which indicates the unit being formatted; literals which are
part of the larger frame will not have this property.



 
Examples
--------


 
### Using formatToParts 

 
 
 
[js]


```js
const rtf = new Intl.RelativeTimeFormat("en", { numeric: "auto" });

// Format relative time using the day unit
rtf.formatToParts(-1, "day");
// [{ type: "literal", value: "yesterday"}]

rtf.formatToParts(100, "day");
// [
//   { type: "literal", value: "in " },
//   { type: "integer", value: "100", unit: "day" },
//   { type: "literal", value: " days" }
// ]
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.RelativeTimeFormat.prototype.formatToParts]](https://tc39.es/ecma402/#sec-Intl.RelativeTimeFormat.prototype.formatToParts)

  ---------------------------------------------------------------------------------------------------------------------------------------------


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

`formatToParts`

71

79

70

58

14

71

79

50

14

10.0

71

1.8

12.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `RelativeTimeFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/RelativeTimeFormat/RelativeTimeFormat)
for more details.

 
See also 
--------

 
-   [`Intl.RelativeTimeFormat`](../relativetimeformat)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/RelativeTimeFormat/formatToParts>

