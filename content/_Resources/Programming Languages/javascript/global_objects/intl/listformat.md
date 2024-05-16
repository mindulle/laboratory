Intl.ListFormat
===============

 
The `Intl.ListFormat` object enables language-sensitive list formatting.


 
Try it 
------

 



 
Constructor
-----------

 

[`Intl.ListFormat()`](listformat/listformat)

:   Creates a new `Intl.ListFormat` object.



 
Static methods 
--------------

 

[`Intl.ListFormat.supportedLocalesOf()`](listformat/supportedlocalesof)

:   Returns an array containing those of the provided locales that are
    supported without having to fall back to the runtime\'s default
    locale.



 
Instance properties 
-------------------

 
These properties are defined on `Intl.ListFormat.prototype` and shared
by all `Intl.ListFormat` instances.

[`Intl.ListFormat.prototype.constructor`](../object/constructor)

:   The constructor function that created the instance object. For
    `Intl.ListFormat` instances, the initial value is the
    [`Intl.ListFormat`](listformat/listformat) constructor.

[`Intl.ListFormat.prototype[@@toStringTag]`](#intl.listformat.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](../symbol/tostringtag)
    property is the string `"Intl.ListFormat"`. This property is used in
    [`Object.prototype.toString()`](../object/tostring).



 
Instance methods 
----------------

 

[`Intl.ListFormat.prototype.format()`](listformat/format)

:   Returns a language-specific formatted string representing the
    elements of the list.

[`Intl.ListFormat.prototype.formatToParts()`](listformat/formattoparts)

:   Returns an array of objects representing the different components
    that can be used to format a list of values in a locale-aware
    fashion.

[`Intl.ListFormat.prototype.resolvedOptions()`](listformat/resolvedoptions)

:   Returns a new object with properties reflecting the locale and style
    formatting options computed during the construction of the current
    [`Intl.ListFormat`](listformat) object.



 
Examples
--------


 
### Using format 

 
The following example shows how to create a List formatter using the
English language.

 
 
[js]


```js
const list = ["Motorcycle", "Bus", "Car"];

console.log(
  new Intl.ListFormat("en-GB", { style: "long", type: "conjunction" }).format(
    list,
  ),
);
// Motorcycle, Bus and Car

console.log(
  new Intl.ListFormat("en-GB", { style: "short", type: "disjunction" }).format(
    list,
  ),
);
// Motorcycle, Bus or Car

console.log(
  new Intl.ListFormat("en-GB", { style: "narrow", type: "unit" }).format(list),
);
// Motorcycle Bus Car
```




 
### Using formatToParts 

 
The following example shows how to create a List formatter returning
formatted parts

 
 
[js]


```js
const list = ["Motorcycle", "Bus", "Car"];
console.log(
  new Intl.ListFormat("en-GB", {
    style: "long",
    type: "conjunction",
  }).formatToParts(list),
);

// [ { "type": "element", "value": "Motorcycle" },
//   { "type": "literal", "value": ", " },
//   { "type": "element", "value": "Bus" },
//   { "type": "literal", "value": ", and " },
//   { "type": "element", "value": "Car" } ];
```




Specifications
--------------

 
  ---------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  listformat-objects]](https://tc39.es/ecma402/#listformat-objects)

  ---------------------------------------------------------------------------


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

`ListFormat`

72

79

78

60

14.1Only available on macOS Big Sur (11) and above.

72

79

51

14.5

11.0

72

1.8

13.0.0

12.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. When other locales are specified, the `ListFormat`
instance silently falls back to `en-US`. To make full ICU (locale) data
available before version 13, see [Node.js documentation on the
`--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

`ListFormat`

72

79

78

60

14.1Only available on macOS Big Sur (11) and above.

72

79

51

14.5

11.0

72

1.8

12.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `ListFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/ListFormat)
for more details.

`format`

72

79

78

60

14.1Only available on macOS Big Sur (11) and above.

72

79

51

14.5

11.0

72

1.8

12.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `ListFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/ListFormat)
for more details.

`formatToParts`

72

79

78

60

14.1Only available on macOS Big Sur (11) and above.

72

79

51

14.5

11.0

72

1.8

12.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `ListFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/ListFormat)
for more details.

`resolvedOptions`

72

79

78

60

14.1Only available on macOS Big Sur (11) and above.

72

79

51

14.5

11.0

72

1.8

12.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `ListFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/ListFormat)
for more details.

`supportedLocalesOf`

72

79

78

60

14.1Only available on macOS Big Sur (11) and above.

72

79

51

14.5

11.0

72

1.8

13.0.0

12.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. To make full ICU (locale) data available before
version 13, see [Node.js documentation on the `--with-intl`
option](https://nodejs.org/docs/latest/api/intl.html#intl_options_for_building_node_js)
and how to provide the data.

 
See also 
--------

 
-   [Polyfill of `Intl.ListFormat` in
    FormatJS](https://formatjs.io/docs/polyfills/intl-listformat/)
-   [`Intl`](../intl)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat>

