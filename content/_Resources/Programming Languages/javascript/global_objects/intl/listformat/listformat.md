Intl.ListFormat() constructor
=============================

 
The `Intl.ListFormat()` constructor creates
[`Intl.ListFormat`](../listformat) objects.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Intl.ListFormat()
new Intl.ListFormat(locales)
new Intl.ListFormat(locales, options)
```


 
**Note:** `Intl.ListFormat()` can only be constructed with
[`new`](../../../operators/new). Attempting to call it without `new`
throws a [`TypeError`](../../typeerror).




 
### Parameters

 

[`locales`](#locales) [Optional]

:   A string with a BCP 47 language tag or an [`Intl.Locale`](../locale)
    instance, or an array of such locale identifiers. For the general
    form and interpretation of the `locales` argument, see [the
    parameter description on the `Intl` main
    page](../../intl#locales_argument).

[`options`](#options) [Optional]

:   An object containing the following properties, in the order they are
    retrieved (all of them are optional):

    [`localeMatcher`](#localematcher)

    :   The locale matching algorithm to use. Possible values are
        `"lookup"` and `"best fit"`; the default is `"best fit"`. For
        information about this option, see [Locale identification and
        negotiation](../../intl#locale_identification_and_negotiation).

    [`type`](#type)

    :   Indicates the type of grouping. Possible values are:

        [`"conjunction"`](#conjunction) (default)

        :   For \"and\"-based grouping of the list items: \"A, B, and
            C\"

        [`"disjunction"`](#disjunction)

        :   For \"or\"-based grouping of the list items: \"A, B, or C\"

        [`"unit"`](#unit)

        :   For grouping the list items as a unit (neither \"and\"-based
            nor \"or\"-based): \"A, B, C\"

    [`style`](#style)

    :   The grouping style (for example, whether list separators and
        conjunctions are included). Possible values are:

        [`"long"`](#long) (default)

        :   E.g. \"A, B, and C\"

        [`"short"`](#short)

        :   E.g. \"A, B, C\"

        [`"narrow"`](#narrow)

        :   E.g. \"A B C\"



 
### Exceptions

 

[`RangeError`](../../rangeerror)

:   Thrown if `locales` or `options` contain invalid values.



 
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

console.log(new Intl.ListFormat("en-GB", { style: "long" }).format(list));
// Motorcycle, Bus and Car

console.log(new Intl.ListFormat("en-US", { style: "long" }).format(list));
// Motorcycle, Bus, and Car

console.log(
  new Intl.ListFormat("en-GB", { style: "short", type: "conjunction" }).format(
    list,
  ),
);
// Motorcycle, Bus and Car

console.log(
  new Intl.ListFormat("en-US", { style: "short", type: "conjunction" }).format(
    list,
  ),
);
// Motorcycle, Bus, & Car

console.log(
  new Intl.ListFormat("en-GB", { style: "narrow", type: "conjunction" }).format(
    list,
  ),
);
// Motorcycle, Bus, Car

console.log(
  new Intl.ListFormat("en-GB", { style: "long", type: "disjunction" }).format(
    list,
  ),
);
// Motorcycle, Bus or Car

console.log(
  new Intl.ListFormat("en-GB", { style: "short", type: "disjunction" }).format(
    list,
  ),
);
// Motorcycle, Bus or Car

console.log(
  new Intl.ListFormat("en-GB", { style: "narrow", type: "disjunction" }).format(
    list,
  ),
);
// Motorcycle, Bus or Car

console.log(new Intl.ListFormat("en-US", { style: "narrow" }).format(list));
// Motorcycle, Bus, Car

console.log(
  new Intl.ListFormat("en-GB", { style: "narrow", type: "unit" }).format(list),
);
// Motorcycle Bus Car

console.log(
  new Intl.ListFormat("en-US", { style: "long" }).format([
    "30 degrees",
    "15 minutes",
    "50 seconds",
  ]),
);
// 30 degrees, 15 minutes, and 50 seconds

console.log(
  new Intl.ListFormat("en-US", { style: "narrow" }).format([
    "30 degrees",
    "15 minutes",
    "50 seconds",
  ]),
);
// 30 degrees, 15 minutes, 50 seconds

console.log(
  new Intl.ListFormat("en-US", { style: "narrow", type: "unit" }).format([
    "30°",
    "15′",
    "50″",
  ]),
);
// 30° 15′ 50″
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl-listformat-constructor]](https://tc39.es/ecma402/#sec-intl-listformat-constructor)

  -----------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [`Intl.ListFormat`](../listformat)
-   [`Intl`](../../intl)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/ListFormat>

