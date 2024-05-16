Intl.DurationFormat.prototype.resolvedOptions()
===============================================

 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `resolvedOptions()` method of
[`Intl.DurationFormat`](../durationformat) instances returns a new
object with properties reflecting the locale and date and time
formatting options computed during initialization of this
[`Intl.DurationFormat`](../durationformat) object.


 
Syntax
------

 
 
 
[js]


```js
resolvedOptions()
```




 
### Parameters

 
None.



 
### Return value 

 
A new object with properties reflecting the locale and date and time
formatting options computed during the initialization of the given
[`Intl.DateTimeFormat`](../datetimeformat) object.



 
Description
-----------

 
The resulting object has the following properties:

[`locale`](#locale)

:   The [BCP 47 language
    tag](https://datatracker.ietf.org/doc/html/rfc5646) for the locale
    used. If any Unicode extension values were requested in the input
    BCP 47 language tag that led to this locale, the key-value pairs
    that were requested and are supported for this locale are included
    in `locale`.

[`style`](#style)

:   One of the strings `"long"`, `"short"`, `"narrow"`, or `"digital"`
    identifying the duration formatting style used.

[`years`](#years)

:   One of the strings `"long"`, `"short"`, or `"narrow"` identifying
    the formatting style used for the `years` field.

[`yearsDisplay`](#yearsdisplay)

:   One of the strings `"auto"` or `"always"` identifying when to
    display the `years` field.

[`months`](#months)

:   One of the strings `"long"`, `"short"`, `and "narrow"` identifying
    the formatting style used for the `months` field.

[`monthsDisplay`](#monthsdisplay)

:   One of the strings `"auto"` or `"always"` identifying when to
    display the `months` field.

[`weeks`](#weeks)

:   One of the strings `"long"`, `"short"`, `and "narrow"` identifying
    the formatting style used for the `weeks` field.

[`weeksDisplay`](#weeksdisplay)

:   One of the strings `"auto"` or `"always"` identifying when to
    display the `weeks` field.

[`days`](#days)

:   One of the strings `"long"`, `"short"`, and `"narrow"` identifying
    the formatting style used for the `days` field.

[`daysDisplay`](#daysdisplay)

:   One of the strings `"auto"` or `"always"` identifying when to
    display the `days` field.

[`hours`](#hours)

:   One of the strings `"long"`, `"short"`, `"narrow"`, `"2-digit"`, or
    `"numeric"` identifying the formatting style used for the `hours`
    field.

[`hoursDisplay`](#hoursdisplay)

:   One of the strings `"auto"` or `"always"` identifying when to
    display the `hours` field.

[`minutes`](#minutes)

:   One of the strings `"long"`, `"short"`, `"narrow"`, `"2-digit"`, or
    `"numeric"` identifying the formatting style used for the `minutes`
    field.

[`minutesDisplay`](#minutesdisplay)

:   One of the strings `"auto"` or `"always"` identifying when to
    display the `minutes` field.

[`seconds`](#seconds)

:   One of the strings `"long"`, `"short"`, `"narrow"`, `"2-digit"`, or
    `"numeric"` identifying the formatting style used for the `seconds`
    field.

[`secondsDisplay`](#secondsdisplay)

:   One of the strings `"auto"` or `"always"` identifying when to
    display the `seconds` field.

[`milliseconds`](#milliseconds)

:   One of the strings `"long"`, `"short"`, `"narrow"`, or `"numeric"`
    identifying the formatting style used for the `milliseconds` field.

[`millisecondsDisplay`](#millisecondsdisplay)

:   One of the strings `"auto"` or `"always"` identifying when to
    display the `millisecondsDisplay` field.

[`microseconds`](#microseconds)

:   One of the strings `"long"`, `"short"`, `"narrow"`, or `"numeric"`
    identifying the formatting style used for the `microseconds` field.

[`microsecondsDisplay`](#microsecondsdisplay)

:   One of the strings `"auto"` or `"always"` identifying when to
    display the `microsecondsDisplay` field.

[`nanoseconds`](#nanoseconds)

:   One of the strings `"long"`, `"short"`, `"narrow"`, or `"numeric"`
    identifying the formatting style used for the `nanoseconds` field.

[`nanosecondsDisplay`](#nanosecondsdisplay)

:   One of the strings `"auto"` or `"always"` identifying when to
    display the `nanosecondsDisplay` field.

[`fractionalDigits`](#fractionaldigits)

:   A number, identifying the number of fractional digits used with
    numeric styles.

[`numberingSystem`](#numberingsystem)

:   The value provided for this property in the options argument, if
    present, or the value requested using the Unicode extension key `nu`
    or filled in as a default.



 
Examples
--------


 
### Using the resolvedOptions method 

 
 
 
[js]


```js
const duration = new Intl.DurationFormat("en");
const usedOptions = duration.resolvedOptions();

usedOptions.locale; // "en"
usedOptions.numberingSystem; // "latn"
usedOptions.years; // "long"
usedOptions.yearsDisplay; // "auto"
usedOptions.style; // "long"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Intl.DurationFormat\
  [\#
  sec-Intl.DurationFormat.prototype.resolvedOptions]](https://tc39.es/proposal-intl-duration-format/#sec-Intl.DurationFormat.prototype.resolvedOptions)

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`resolvedOptions`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DurationFormat/resolvedOptions>

