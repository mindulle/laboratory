Intl.RelativeTimeFormat
=======================

 
The `Intl.RelativeTimeFormat` object enables language-sensitive relative
time formatting.


 
Try it 
------

 



 
Constructor
-----------

 

[`Intl.RelativeTimeFormat()`](relativetimeformat/relativetimeformat)

:   Creates a new `Intl.RelativeTimeFormat` object.



 
Static methods 
--------------

 

[`Intl.RelativeTimeFormat.supportedLocalesOf()`](relativetimeformat/supportedlocalesof)

:   Returns an array containing those of the provided locales that are
    supported without having to fall back to the runtime\'s default
    locale.



 
Instance properties 
-------------------

 
These properties are defined on `Intl.RelativeTimeFormat.prototype` and
shared by all `Intl.RelativeTimeFormat` instances.

[`Intl.RelativeTimeFormat.prototype.constructor`](../object/constructor)

:   The constructor function that created the instance object. For
    `Intl.RelativeTimeFormat` instances, the initial value is the
    [`Intl.RelativeTimeFormat`](relativetimeformat/relativetimeformat)
    constructor.

[`Intl.RelativeTimeFormat.prototype[@@toStringTag]`](#intl.relativetimeformat.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](../symbol/tostringtag)
    property is the string `"Intl.RelativeTimeFormat"`. This property is
    used in [`Object.prototype.toString()`](../object/tostring).



 
Instance methods 
----------------

 

[`Intl.RelativeTimeFormat.prototype.format()`](relativetimeformat/format)

:   Formats a `value` and a `unit` according to the locale and
    formatting options of the given `Intl.RelativeTimeFormat` object.

[`Intl.RelativeTimeFormat.prototype.formatToParts()`](relativetimeformat/formattoparts)

:   Returns an [`Array`](../array) of objects representing the relative
    time format in parts that can be used for custom locale-aware
    formatting.

[`Intl.RelativeTimeFormat.prototype.resolvedOptions()`](relativetimeformat/resolvedoptions)

:   Returns a new object with properties reflecting the locale and
    formatting options computed during initialization of the object.



 
Examples
--------


 
### Basic format usage 

 
The following example shows how to use a relative time formatter for the
English language.

 
 
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




 
### Using formatToParts 

 
The following example shows how to create a relative time formatter
returning formatted parts.

 
 
[js]


```js
const rtf = new Intl.RelativeTimeFormat("en", { numeric: "auto" });

// Format relative time using the day unit.
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

 
  -------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  relativetimeformat-objects]](https://tc39.es/ecma402/#relativetimeformat-objects)

  -------------------------------------------------------------------------------------------


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

`RelativeTimeFormat`

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

13.0.0

12.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. When other locales are specified, the
`RelativeTimeFormat` instance silently falls back to `en-US`. To make
full ICU (locale) data available before version 13, see [Node.js
documentation on the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

`RelativeTimeFormat`

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

`resolvedOptions`

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

`supportedLocalesOf`

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

13.0.0

12.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. To make full ICU (locale) data available before
version 13, see [Node.js documentation on the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

 
See also 
--------

 
-   [Polyfill of `Intl.RelativeTimeFormat` in
    FormatJS](https://formatjs.io/docs/polyfills/intl-relativetimeformat/)
-   [`Intl`](../intl)
-   [`Intl.RelativeTimeFormat`](https://v8.dev/features/intl-relativetimeformat)
    on v8.dev (2018)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/RelativeTimeFormat>

