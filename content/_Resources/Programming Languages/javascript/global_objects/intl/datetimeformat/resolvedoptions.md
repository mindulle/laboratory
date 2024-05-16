Intl.DateTimeFormat.prototype.resolvedOptions()
===============================================

 
The `resolvedOptions()` method of
[`Intl.DateTimeFormat`](../datetimeformat) instances returns a new
object with properties reflecting the locale and date and time
formatting options computed during initialization of this
`Intl.DateTimeFormat` object.


 
Try it 
------

 



 
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

:   The BCP 47 language tag for the locale actually used. If any Unicode
    extension values were requested in the input BCP 47 language tag
    that led to this locale, the key-value pairs that were requested and
    are supported for this locale are included in `locale`.

[`calendar`](#calendar)

:   E.g. \"gregory\"

[`numberingSystem`](#numberingsystem)

:   The values requested using the Unicode extension keys `"ca"` and
    `"nu"` or filled in as default values.

[`timeZone`](#timezone)

:   The value provided for this property in the `options` argument;
    defaults to the runtime\'s default time zone. Should never be
    `undefined`.

[`hour12`](#hour12)

:   The value provided for this property in the `options` argument or
    filled in as a default.

[`weekday`](#weekday), `era`, `year`, `month`, `day`, `hour`, `minute`, `second`, `timeZoneName`

:   The values resulting from format matching between the corresponding
    properties in the `options` argument and the available combinations
    and representations for date-time formatting in the selected locale.
    Some of these properties may not be present, indicating that the
    corresponding components will not be represented in formatted
    output.



 
Examples
--------


 
### Using the resolvedOptions method 

 
 
 
[js]


```js
const germanFakeRegion = new Intl.DateTimeFormat("de-XX", { timeZone: "UTC" });
const usedOptions = germanFakeRegion.resolvedOptions();

usedOptions.locale; // "de"
usedOptions.calendar; // "gregory"
usedOptions.numberingSystem; // "latn"
usedOptions.timeZone; // "UTC"
usedOptions.month; // "numeric"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.datetimeformat.prototype.resolvedoptions]](https://tc39.es/ecma402/#sec-intl.datetimeformat.prototype.resolvedoptions)

  -----------------------------------------------------------------------------------------------------------------------------------------


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

24

12

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
available by default. See [the `DateTimeFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/DateTimeFormat)
for more details.

`computed_timezone`

35

14

53

30

10

35

56

22

10

3.0

37

1.8

8.10.0

 
See also 
--------

 
-   [`Intl.DateTimeFormat`](../datetimeformat)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/resolvedOptions>

