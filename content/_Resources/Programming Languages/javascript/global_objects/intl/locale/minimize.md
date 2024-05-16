Intl.Locale.prototype.minimize()
================================

 
The `minimize()` method of [`Intl.Locale`](../locale) instances attempts
to remove information about this locale that would be added by calling
[`maximize()`](maximize).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
minimize()
```




 
### Parameters

 
None.



 
### Return value 

 
A [`Intl.Locale`](../locale) instance whose `baseName` property returns
the result of the [Remove Likely
Subtags](https://www.unicode.org/reports/tr35/#Likely_Subtags) algorithm
executed against *[`locale.baseName`](basename)*.



 
Description
-----------

 
This method carries out the reverse of [`maximize()`](maximize),
removing any language, script, or region subtags from the locale
language identifier (essentially the contents of `baseName`). This is
useful when there are superfluous subtags in the language identifier;
for instance, \"en-Latn\" can be simplified to \"en\", since \"Latn\" is
the only script used to write English. `minimize()` only affects the
main subtags that comprise the [language
identifier](https://www.unicode.org/reports/tr35/#Language_Locale_Field_Definitions):
language, script, and region subtags. Other subtags after the \"-u\" in
the locale identifier are called extension subtags and are not affected
by the `minimize()` method. Examples of these subtags include
[`hourCycle`](hourcycle), [`calendar`](calendar), and
[`numeric`](numeric).



 
Examples
--------


 
### Using minimize 

 
 
 
[js]


```js
const myLocale = new Intl.Locale("fr-Latn-FR", {
  hourCycle: "h12",
  calendar: "gregory",
});
console.log(myLocale.baseName); // Prints "fr-Latn-FR"
console.log(myLocale.toString()); // Prints "fr-Latn-FR-u-ca-gregory-hc-h12"

const myLocMinimized = myLocale.minimize();

// Prints "fr", since French is only written in the Latin script
// and is most likely to be spoken in France.
console.log(myLocMinimized.baseName);

// Prints "fr-u-ca-gregory-hc-h12".
// Note that the extension tags (after "-u") remain unchanged.
console.log(myLocMinimized.toString());
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.Locale.prototype.minimize]](https://tc39.es/ecma402/#sec-Intl.Locale.prototype.minimize)

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

`minimize`

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



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/minimize>

