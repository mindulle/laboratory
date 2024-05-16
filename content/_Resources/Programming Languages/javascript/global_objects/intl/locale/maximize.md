Intl.Locale.prototype.maximize()
================================

 
The `maximize()` method of [`Intl.Locale`](../locale) instances gets the
most likely values for the language, script, and region of this locale
based on existing values.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
maximize()
```




 
### Parameters

 
None.



 
### Return value 

 
A [`Intl.Locale`](../locale) instance whose `baseName` property returns
the result of the [Add Likely
Subtags](https://www.unicode.org/reports/tr35/#Likely_Subtags) algorithm
executed against *[`locale.baseName`](basename)*.



 
Description
-----------

 
Sometimes, it is convenient to be able to identify the most likely
locale language identifier subtags based on an incomplete language ID.
The Add Likely Subtags algorithm gives us this functionality. For
instance, given the language ID \"en\", the algorithm would return
\"en-Latn-US\", since English can only be written in the Latin script,
and is most likely to be used in the United States, as it is the largest
English-speaking country in the world. This functionality is provided to
JavaScript programmers via the `maximize()` method. `maximize()` only
affects the main subtags that comprise the [language
identifier](https://www.unicode.org/reports/tr35/#Language_Locale_Field_Definitions):
language, script, and region subtags. Other subtags after the \"-u\" in
the locale identifier are called extension subtags and are not affected
by the `maximize()` method. Examples of these subtags include
[`hourCycle`](hourcycle), [`calendar`](calendar), and
[`numeric`](numeric).



 
Examples
--------


 
### Using maximize 

 
 
 
[js]


```js
const myLocale = new Intl.Locale("fr", {
  hourCycle: "h12",
  calendar: "gregory",
});
console.log(myLocale.baseName); // Prints "fr"
console.log(myLocale.toString()); // Prints "fr-u-ca-gregory-hc-h12"
const myLocMaximized = myLocale.maximize();

// Prints "fr-Latn-FR". The "Latn" and "FR" tags are added,
// since French is only written in the Latin script and is most likely to be spoken in France.
console.log(myLocMaximized.baseName);

// Prints "fr-Latn-FR-u-ca-gregory-hc-h12".
// Note that the extension tags (after "-u") remain unchanged.
console.log(myLocMaximized.toString());
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.Locale.prototype.maximize]](https://tc39.es/ecma402/#sec-Intl.Locale.prototype.maximize)

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

`maximize`

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
-   [`baseName`](basename)
-   [Likely
    Subtags](https://www.unicode.org/reports/tr35/#Likely_Subtags) in
    the Unicode locale data markup language spec



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/maximize>

