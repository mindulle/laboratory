Intl.Locale.prototype.baseName
==============================

 
The `baseName` accessor property of [`Intl.Locale`](../locale) instances
returns a substring of this locale\'s string representation, containing
core information about this locale.


 
Description
-----------

 
An [`Intl.Locale`](../locale) object represents a parsed local and
options for that locale. The `baseName` property returns basic, core
information about the Locale in the form of a substring of the complete
data string. Specifically, the property returns the substring containing
the language, and the script and region if available.

`baseName` returns the
`language ["-" script] ["-" region] *("-" variant)` subsequence of the
[unicode\_language\_id
grammar](https://www.unicode.org/reports/tr35/#Identifiers).



 
Examples
--------


 
### Basic Example 

 
 
 
[js]


```js
const myLoc = new Intl.Locale("fr-Latn-CA"); // Sets locale to Canadian French
console.log(myLoc.toString()); // Prints out "fr-Latn-CA-u-ca-gregory"
console.log(myLoc.baseName); // Prints out "fr-Latn-CA"
```




 
### Example with options in the input string 

 
 
 
[js]


```js
// Sets language to Japanese, region to Japan,

// calendar to Gregorian, hour cycle to 24 hours
const japan = new Intl.Locale("ja-JP-u-ca-gregory-hc-24");
console.log(japan.toString()); // Prints out "ja-JP-u-ca-gregory-hc-h24"
console.log(japan.baseName); // Prints out "ja-JP"
```




 
### Example with options that override input string 

 
 
 
[js]


```js
// Input string indicates language as Dutch and region as Belgium,

// but options object overrides the region and sets it to the Netherlands
const dutch = new Intl.Locale("nl-Latn-BE", { region: "NL" });

console.log(dutch.baseName); // Prints out "nl-Latn-NL"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.Locale.prototype.baseName]](https://tc39.es/ecma402/#sec-Intl.Locale.prototype.baseName)

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

`baseName`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/baseName>

