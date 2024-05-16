Intl.RelativeTimeFormat.prototype.format()
==========================================

 
The `format()` method of
[`Intl.RelativeTimeFormat`](../relativetimeformat) instances formats a
`value` and `unit` according to the locale and formatting options of
this `Intl.RelativeTimeFormat` object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
format(value, unit)
```




 
### Parameters

 

[`value`](#value)

:   Numeric value to use in the internationalized relative time message.

[`unit`](#unit)

:   Unit to use in the relative time internationalized message. Possible
    values are: `"year"`, `"quarter"`, `"month"`, `"week"`, `"day"`,
    `"hour"`, `"minute"`, `"second"`. Plural forms are also permitted.



 
### Return value 

 
A string representing the given `value` and `unit` formatted according
to the locale and formatting options of this
[`Intl.RelativeTimeFormat`](../relativetimeformat) object.



 
Examples
--------


 
### Basic format usage 

 
The following example shows how to create a relative time formatter
using the English language.

 
 
[js]


```js
// Create a relative time formatter in your locale
// with default values explicitly passed in.
const rtf = new Intl.RelativeTimeFormat("en", {
  localeMatcher: "best fit", // other values: "lookup"
  numeric: "always", // other values: "auto"
  style: "long", // other values: "short" or "narrow"
});

// Format relative time using negative value (-1).
rtf.format(-1, "day"); // "1 day ago"

// Format relative time using positive value (1).
rtf.format(1, "day"); // "in 1 day"
```




 
### Using the auto option 

 
If `numeric:auto` option is passed, it will produce the string
`yesterday`, `today`, or `tomorrow` instead of `1 day ago`, `in 0 days`,
or `in 1 day`. This allows to not always have to use numeric values in
the output.

 
 
[js]


```js
// Create a relative time formatter in your locale
// with numeric: "auto" option value passed in.
const rtf = new Intl.RelativeTimeFormat("en", { numeric: "auto" });

// Format relative time using negative value (-1).
rtf.format(-1, "day"); // "yesterday"

rtf.format(0, "day"); // "today"

// Format relative time using positive day unit (1).
rtf.format(1, "day"); // "tomorrow"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.RelativeTimeFormat.prototype.format]](https://tc39.es/ecma402/#sec-Intl.RelativeTimeFormat.prototype.format)

  -------------------------------------------------------------------------------------------------------------------------------


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

71

79

65

58

14

71

65

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/RelativeTimeFormat/format>

