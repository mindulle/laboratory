Intl.Locale.prototype.numeric
=============================

 
The `numeric` accessor property of [`Intl.Locale`](../locale) instances
returns whether this locale has special collation handling for numeric
characters.


 
Description
-----------

 
Like [`caseFirst`](casefirst), `numeric` represents a modification to
the collation rules utilized by the locale. `numeric` is a boolean
value, which means that it can be either `true` or `false`. If `numeric`
is set to `false`, there will be no special handling of numeric values
in strings. If `numeric` is set to `true`, then the locale will take
numeric characters into account when collating strings. This special
numeric handling means that sequences of decimal digits will be compared
as numbers. For example, the string \"A-21\" will be considered less
than \"A-123\".



 
Examples
--------


 
### Setting the numeric value via the locale string 

 
In the [Unicode locale string
spec](https://www.unicode.org/reports/tr35/), the values that `numeric`
represents correspond to the key `kn`. `kn` is considered a locale
string \"extension subtag\". These subtags add additional data about the
locale, and are added to locale identifiers by using the `-u` extension
key. Thus, the `numeric` value can be added to the initial locale
identifier string that is passed into the [`Intl.Locale()`](locale)
constructor. To set the `numeric` value, first add the `-u` extension
key to the string. Next, add the `-kn` extension key to indicate that
you are adding a value for `numeric`. Finally, add the `numeric` value
to the string. If you want to set `numeric` to `true`, adding the `kn`
key will suffice. To set the value to `false`, you must specify in by
adding `"false"` after the `kn` key.

 
 
[js]


```js
const locale = new Intl.Locale("fr-Latn-FR-u-kn-false");
console.log(locale.numeric); // Prints "false"
```




 
### Setting the numeric value via the configuration object argument 

 
The [`Intl.Locale()`](locale) constructor has an optional configuration
object argument, which can be used to pass extension types. Set the
`numeric` property of the configuration object to your desired `numeric`
value and pass it into the constructor.

 
 
[js]


```js
const locale = new Intl.Locale("en-Latn-US", { numeric: true });
console.log(locale.numeric); // Prints "true"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.Locale.prototype.numeric]](https://tc39.es/ecma402/#sec-Intl.Locale.prototype.numeric)

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

`numeric`

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



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/numeric>

