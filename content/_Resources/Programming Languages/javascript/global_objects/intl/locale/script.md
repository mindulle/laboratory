Intl.Locale.prototype.script
============================

 
The `script` accessor property of [`Intl.Locale`](../locale) instances
returns the script used for writing the particular language used in this
locale.


 
Description
-----------

 
A script, sometimes called writing system, is one of the core attributes
of a locale. It indicates the set of symbols, or glyphs, that are used
to write a particular language. For instance, the script associated with
English is Latin, whereas the script typically associated with Korean is
Hangul. In many cases, denoting a script is not strictly necessary,
since the language (which is necessary) is only written in a single
script. There are exceptions to this rule, however, and it is important
to indicate the script whenever possible, in order to have a complete
Unicode language identifier.



 
Examples
--------


 
### Setting the script in the locale identifier string argument 

 
The script is the second part of a valid Unicode language identifier
string, and can be set by adding it to the locale identifier string that
is passed into the [`Intl.Locale()`](locale) constructor. Note that the
script is not a required part of a locale identifier.

 
 
[js]


```js
const locale = new Intl.Locale("en-Latn-US");
console.log(locale.script); // Prints "Latn"
```




 
### Setting the script via the configuration object 

 
The [`Intl.Locale()`](locale) constructor takes a configuration object,
which can be used to set the script subtag and property.

 
 
[js]


```js
const locale = new Intl.Locale("fr-FR", { script: "Latn" });
console.log(locale.script); // Prints "Latn"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.Locale.prototype.script]](https://tc39.es/ecma402/#sec-Intl.Locale.prototype.script)

  -------------------------------------------------------------------------------------------------------


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

`script`

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
-   [Unicode script
    subtag](https://www.unicode.org/reports/tr35/#unicode_script_subtag_validity)
    in the Unicode locale data markup language spec



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/script>

