Intl.PluralRules.prototype.selectRange()
========================================

 
The `selectRange()` method of [`Intl.PluralRules`](../pluralrules)
instances receives two values and returns a string indicating which
plural rule to use for locale-aware formatting of the indicated range.


 
Syntax
------

 
 
 
[js]


```js
selectRange(startRange, endRange)
```




 
### Parameters

 

[`startRange`](#startrange)

:   A number representing the start of the range.

[`endRange`](#endrange)

:   A number representing the end of the range.



 
### Return value 

 
A string representing the pluralization category of the specified range.
This can be one of `zero`, `one`, `two`, `few`, `many` or `other`, that
are relevant for the locale whose localization is specified in [LDML
Language Plural
Rules](https://www.unicode.org/cldr/charts/43/supplemental/language_plural_rules.html).



 
Description
-----------

 
This function selects a pluralization category according to the locale
and formatting options of an [`Intl.PluralRules`](../pluralrules)
object.

Conceptually the behavior is the same as getting plural rules for a
single cardinal or ordinal number. Languages have one or more forms for
describing ranges, and this method returns the appropriate form given
the supplied locale and formatting options. In English there is only one
plural form, such as \"1--10 apples\", and the method will return
`other`. Other languages can have many forms.



 
Examples
--------


 
### Using selectRange() 

 
 
 
[js]


```js
new Intl.PluralRules("sl").selectRange(102, 201); // 'few'

new Intl.PluralRules("pt").selectRange(102, 102); // 'other'
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.pluralrules.prototype.selectrange]](https://tc39.es/ecma402/#sec-intl.pluralrules.prototype.selectrange)

  ---------------------------------------------------------------------------------------------------------------------------


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

`selectRange`

106

106

116

92

15.4

106

116

72

15.4

20.0

106

No

19.0.0

 
See also 
--------

 
-   [`Intl.PluralRules`](../pluralrules)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/PluralRules/selectRange>

