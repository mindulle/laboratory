Intl.Locale.prototype.caseFirst
===============================

 
The `caseFirst` accessor property of [`Intl.Locale`](../locale)
instances returns whether case is taken into account for this locale\'s
collation rules.


 
Description
-----------

 
A locale\'s collation rules are used to determine how strings are
ordered in that locale. Certain locales use a character\'s case
(UPPERCASE or lowercase) in the collation process. This additional rule
can be expressed in a [`Intl.Locale`](../locale) object\'s `caseFirst`
property.

There are 3 values that the `caseFirst` property can have, outlined in
the table below.



 
### `caseFirst` values 

 
 
  Value     Description
  --------- --------------------------------------------
  `upper`   Upper case to be sorted before lower case.
  `lower`   Lower case to be sorted before upper case.
  `false`   No special case ordering.




 
Examples
--------


 
### Setting the caseFirst value via the locale string 

 
In the [Unicode locale string
spec](https://www.unicode.org/reports/tr35/), the values that
`caseFirst` represents correspond to the key `kf`. `kf` is treated as a
locale string \"extension subtag\". These subtags add additional data
about the locale, and are added to locale identifiers by using the `-u`
extension key. Thus, the `caseFirst` value can be added to the initial
locale identifier string that is passed into the `Locale` constructor.
To add the `caseFirst` value, first add the `-u` extension key to the
string. Next, add the `-kf` extension key to indicate that you are
adding a value for `caseFirst`. Finally, add the `caseFirst` value to
the string.

 
 
[js]


```js
const locale = new Intl.Locale("fr-Latn-FR-u-kf-upper");
console.log(locale.caseFirst); // Prints "upper"
```




 
### Setting the caseFirst value via the configuration object argument 

 
The [`Intl.Locale()`](locale) constructor has an optional configuration
object argument, which can be used to pass extension types. Set the
`caseFirst` property of the configuration object to your desired
`caseFirst` value, and then pass it into the constructor.

 
 
[js]


```js
const locale = new Intl.Locale("en-Latn-US", { caseFirst: "lower" });
console.log(locale.caseFirst); // Prints "lower"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.Locale.prototype.caseFirst]](https://tc39.es/ecma402/#sec-Intl.Locale.prototype.caseFirst)

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

`caseFirst`

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
-   [Unicode case first collation
    spec](https://github.com/unicode-org/cldr/blob/main/common/bcp47/collation.xml#L49)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/caseFirst>

