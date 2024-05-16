Intl.ListFormat.prototype.resolvedOptions()
===========================================

 
The `resolvedOptions()` method of [`Intl.ListFormat`](../listformat)
instances returns a new object with properties reflecting the locale and
style formatting options computed during the construction of this
`Intl.ListFormat` object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
resolvedOptions()
```




 
### Parameters

 
None.



 
### Return value 

 
An object with properties reflecting the locale and formatting options
computed during the construction of the given
[`Intl.ListFormat`](../listformat) object.



 
Description
-----------

 
The object returned by `resolvedOptions()` has the following properties:

[`locale`](#locale)

:   The BCP 47 language tag for the locale actually used. If any Unicode
    extension values were requested in the input BCP 47 language tag
    that led to this locale, the key-value pairs that were requested and
    are supported for this locale are included in `locale`.

[`style`](#style)

:   The value provided for this property in the `options` argument of
    the constructor or the default value (`"long"`). Its value is either
    `"long"`, `"short"`, or `"narrow"`.

[`type`](#type)

:   The value provided for this property in the `options` argument of
    the constructor or the default value (`"conjunction"`). Its value is
    either `"conjunction"`, `"disjunction"`, or `"unit"`.



 
Examples
--------


 
### Using resolvedOptions 

 
 
 
[js]


```js
const deListFormatter = new Intl.ListFormat("de-DE", { style: "short" });

const usedOptions = de.resolvedOptions();
console.log(usedOptions.locale); // "de-DE"
console.log(usedOptions.style); // "short"
console.log(usedOptions.type); // "conjunction" (the default value)
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.ListFormat.prototype.resolvedoptions]](https://tc39.es/ecma402/#sec-Intl.ListFormat.prototype.resolvedoptions)

  ---------------------------------------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [`Intl.ListFormat`](../listformat)
-   [`Intl.NumberFormat.prototype.resolvedOptions()`](../numberformat/resolvedoptions)
-   [`Intl.Collator.prototype.resolvedOptions()`](../collator/resolvedoptions)
-   [`Intl.DateTimeFormat.prototype.resolvedOptions()`](../datetimeformat/resolvedoptions)
-   [`Intl.PluralRules.prototype.resolvedOptions()`](../pluralrules/resolvedoptions)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/resolvedOptions>

