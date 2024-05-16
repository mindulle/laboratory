Intl.DurationFormat.prototype.formatToParts()
=============================================

 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `formatToParts()` method of
[`Intl.DurationFormat`](../durationformat) instances allows locale-aware
formatting of strings produced by
[`Intl.DurationFormat`](../durationformat) formatters.


 
Syntax
------

 
 
 
[js]


```js
formatToParts(duration)
```




 
### Parameters

 

[`duration`](#duration) [Optional]

:   The duration object to be formatted. It should include some or all
    of the following properties: `"months"`, `"weeks"`, `"days"`,
    `"hours"`, `"minutes"`, `"seconds"`, `"milliseconds"`,
    `"microseconds"`, `"nanoseconds"`.



 
### Return value 

 
An [`Array`](../../array) of objects containing the formatted duration
in parts.



 
Description
-----------

 
The `formatToParts()` method is useful for custom formatting of duration
objects. It returns an [`Array`](../../array) of objects containing the
locale-specific tokens from which it possible to build custom strings
while preserving the locale-specific parts. The structure the
`formatToParts()` method returns, looks like this:

 
 
[js]


```js
[
  { type: "integer", value: "7", unit: "hour" },
  { type: "literal", value: " ", unit: "hour" },
  { type: "unit", value: "hr", unit: "hour" },
  { type: "literal", value: ", " },
  { type: "integer", value: "8", unit: "minute" },
  { type: "literal", value: " ", unit: "minute" },
  { type: "unit", value: "min", unit: "minute" },
];
```




 
Examples
--------

 
The `formatToParts` method enables locale-aware formatting of strings
produced by `DurationFormat` formatters by providing you the string in
parts:

 
 
[js]


```js
const duration = {
  hours: 7,
  minutes: 8,
  seconds: 9,
  milliseconds: 123,
  microseconds: 456,
  nanoseconds: 789,
};

new Intl.DurationFormat("en", { style: "long" }).formatToParts(duration);

// Returned value:
[
  { type: "integer", value: "7", unit: "hour" },
  { type: "literal", value: " ", unit: "hour" },
  { type: "unit", value: "hours", unit: "hour" },
  { type: "literal", value: ", " },
  { type: "integer", value: "8", unit: "minute" },
  { type: "literal", value: " ", unit: "minute" },
  { type: "unit", value: "minutes", unit: "minute" },
  { type: "literal", value: ", " },
  { type: "integer", value: "9", unit: "second" },
  { type: "literal", value: " ", unit: "second" },
  { type: "unit", value: "seconds", unit: "second" },
  { type: "literal", value: ", " },
  { type: "integer", value: "123", unit: "millisecond" },
  { type: "literal", value: " ", unit: "millisecond" },
  { type: "unit", value: "milliseconds", unit: "millisecond" },
  { type: "literal", value: ", " },
  { type: "integer", value: "456", unit: "microsecond" },
  { type: "literal", value: " ", unit: "microsecond" },
  { type: "unit", value: "microseconds", unit: "microsecond" },
  { type: "literal", value: " and " },
  { type: "integer", value: "789", unit: "nanosecond" },
  { type: "literal", value: " ", unit: "nanosecond" },
  { type: "unit", value: "nanoseconds", unit: "nanosecond" },
];
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------
  [Intl.DurationFormat\
  [\#
  sec-Intl.DurationFormat.prototype.formatToParts]](https://tc39.es/proposal-intl-duration-format/#sec-Intl.DurationFormat.prototype.formatToParts)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------


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

No

No

No

No

16.4

No

No

No

16.4

No

No

No

No

 
See also 
--------

 
-   [`Intl.DurationFormat`](../durationformat)
-   [`Intl.supportedValuesOf()`](../supportedvaluesof)
-   [`Intl`](../../intl)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DurationFormat/formatToParts>

