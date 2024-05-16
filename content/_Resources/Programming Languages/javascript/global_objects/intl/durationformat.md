Intl.DurationFormat
===================

 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `Intl.DurationFormat` object enables language-sensitive duration
formatting.


 
Constructor
-----------

 

[`Intl.DurationFormat()`](durationformat/durationformat) [Experimental]

:   Creates a new `Intl.DurationFormat` object.



 
Static methods 
--------------

 

[`Intl.DurationFormat.supportedLocalesOf()`](durationformat/supportedlocalesof) [Experimental]

:   Returns an array containing those of the provided locales that are
    supported without having to fall back to the runtime\'s default
    locale.



 
Instance properties 
-------------------

 
These properties are defined on `Intl.DurationFormat.prototype` and
shared by all `Intl.DurationFormat` instances.

[`Intl.DurationFormat.prototype.constructor`](../object/constructor)

:   The constructor function that created the instance object. For
    `Intl.DurationFormat` instances, the initial value is the
    [`Intl.DurationFormat`](durationformat/durationformat) constructor.

[`Intl.DurationFormat.prototype[@@toStringTag]`](#intl.durationformat.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](../symbol/tostringtag)
    property is the string `"Intl.DurationFormat"`. This property is
    used in [`Object.prototype.toString()`](../object/tostring).



 
Instance methods 
----------------

 

[`Intl.DurationFormat.prototype.format()`](durationformat/format) [Experimental]

:   Getter function that formats a duration according to the locale and
    formatting options of this `DurationFormat` object.

[`Intl.DurationFormat.prototype.formatToParts()`](durationformat/formattoparts) [Experimental]

:   Returns an [`Array`](../array) of objects representing the formatted
    duration in parts.

[`Intl.DurationFormat.prototype.resolvedOptions()`](durationformat/resolvedoptions) [Experimental]

:   Returns a new object with properties reflecting the locale and
    formatting options computed during initialization of the object.



 
Examples
--------


 
### Using Intl.DurationFormat 

 
The examples below show how to use the `Intl.DurationFormat` object to
format a duration object with various locales and styles.

 
 
[js]


```js
const duration = {
  hours: 1,
  minutes: 46,
  seconds: 40,
};

// With style set to "long" and locale "fr-FR"
new Intl.DurationFormat("fr-FR", { style: "long" }).format(duration);
// "1 heure, 46 minutes et 40 secondes"

// With style set to "short" and locale "en"
new Intl.DurationFormat("en", { style: "short" }).format(duration);
// "1 hr, 46 min and 40 sec"

// With style set to "short" and locale "pt"
new Intl.DurationFormat("pt", { style: "narrow" }).format(duration);
// "1h 46min 40s"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------
  [Intl.DurationFormat\
  [\#
  durationformat-objects]](https://tc39.es/proposal-intl-duration-format/#durationformat-objects)

  ---------------------------------------------------------------------------------------------------------


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

`DurationFormat`

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

`DurationFormat`

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

`format`

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

`supportedLocalesOf`

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

 
-   [`Intl`](../intl)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DurationFormat>

