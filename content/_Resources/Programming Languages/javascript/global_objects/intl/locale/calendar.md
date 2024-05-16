Intl.Locale.prototype.calendar
==============================

 
The `calendar` accessor property of [`Intl.Locale`](../locale) instances
returns the calendar type for this locale.


 
Description
-----------

 
While most of the world uses the Gregorian calendar, there are several
regional calendar eras used around the world. The `calendar` property\'s
value is set at construction time, either through the `ca` key of the
locale identifier or through the `calendar` option of the
[`Intl.Locale()`](locale) constructor. The latter takes priority if they
are both present; and if neither is present, the property has value
`undefined`.

For a list of supported calendar types, see
[`Intl.Locale.prototype.getCalendars()`](getcalendars#supported_calendar_types).

The set accessor of `calendar` is `undefined`. You cannot change this
property directly.



 
Examples
--------

 
Like other locale subtags, the calendar type can be added to the
[`Intl.Locale`](../locale) object via the locale string, or a
configuration object argument to the constructor.



 
### Adding a calendar type via the locale string 

 
In the [Unicode locale string
spec](https://www.unicode.org/reports/tr35/), calendar era types are
locale key \"extension subtags\". These subtags add additional data
about the locale, and are added to locale identifiers by using the `-u`
extension. Thus, the calendar era type can be added to the initial
locale identifier string that is passed into the
[`Intl.Locale()`](locale) constructor. To add the calendar type, first
add the `-u` extension to the string. Next, add the `-ca` extension to
indicate that you are adding a calendar type. Finally, add the calendar
era type to the string.

 
 
[js]


```js
const locale = new Intl.Locale("fr-FR-u-ca-buddhist");
console.log(locale.calendar); // Prints "buddhist"
```




 
### Adding a calendar type via the configuration object argument 

 
The [`Intl.Locale()`](locale) constructor has an optional configuration
object argument, which can contain any of several extension types,
including calendars. Set the `calendar` property of the configuration
object to your desired calendar era, and then pass it into the
constructor.

 
 
[js]


```js
const locale = new Intl.Locale("fr-FR", { calendar: "buddhist" });
console.log(locale.calendar); // "buddhist"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.Locale.prototype.calendar]](https://tc39.es/ecma402/#sec-Intl.Locale.prototype.calendar)

  -----------------------------------------------------------------------------------------------------------


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

`calendar`

74

79

75

62

14

74

79

53

14

11.0

74

1.8

12.0.0

 
See also 
--------

 
-   [`Intl.Locale`](../locale)
-   [`Intl.Locale.prototype.getCalendars()`](getcalendars)
-   [Unicode Calendar
    Identifier](https://www.unicode.org/reports/tr35/#UnicodeCalendarIdentifier)
    in the Unicode locale data markup language spec



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/calendar>

