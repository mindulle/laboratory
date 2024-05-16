Intl.Locale.prototype.hourCycle
===============================

 
The `hourCycle` accessor property of [`Intl.Locale`](../locale)
instances returns the hour cycle type for this locale.


 
Description
-----------

 
There are 2 main types of time keeping conventions (clocks) used around
the world: the 12 hour clock and the 24 hour clock. The `hourCycle`
property\'s value is set at construction time, either through the `hc`
key of the locale identifier or through the `hourCycle` option of the
[`Intl.Locale()`](locale) constructor. The latter takes priority if they
are both present; and if neither is present, the property has value
`undefined`.

For a list of supported hour cycle types, see
[`Intl.Locale.prototype.getHourCycles()`](gethourcycles#supported_hour_cycle_types).

The set accessor of `hourCycle` is `undefined`. You cannot change this
property directly.



 
Examples
--------

 
Like other locale subtags, the hour cycle type can be added to the
[`Intl.Locale`](../locale) object via the locale string, or a
configuration object argument to the constructor.



 
### Adding an hour cycle via the locale string 

 
In the [Unicode locale string
spec](https://www.unicode.org/reports/tr35/), hour cycle types are
locale key \"extension subtags\". These subtags add additional data
about the locale, and are added to locale identifiers by using the `-u`
extension. Thus, the hour cycle type can be added to the initial locale
identifier string that is passed into the [`Intl.Locale()`](locale)
constructor. To add the hour cycle type, first add the `-u` extension
key to the string. Next, add the `-hc` extension to indicate that you
are adding an hour cycle. Finally, add the hour cycle type to the
string.

 
 
[js]


```js
const locale = new Intl.Locale("fr-FR-u-hc-h23");
console.log(locale.hourCycle); // "h23"
```




 
### Adding an hour cycle via the configuration object argument 

 
The [`Intl.Locale()`](locale) constructor has an optional configuration
object argument, which can contain any of several extension types,
including hour cycle types. Set the `hourCycle` property of the
configuration object to your desired hour cycle type, and then pass it
into the constructor.

 
 
[js]


```js
const locale = new Intl.Locale("en-US", { hourCycle: "h12" });
console.log(locale.hourCycle); // "h12"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.Locale.prototype.hourCycle]](https://tc39.es/ecma402/#sec-Intl.Locale.prototype.hourCycle)

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

`hourCycle`

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
-   [`Intl.Locale.prototype.getHourCycles()`](gethourcycles)
-   [Unicode Hour Cycle
    Identifier](https://www.unicode.org/reports/tr35/#UnicodeHourCycleIdentifier)
    in the Unicode locale data markup language spec



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/hourCycle>

