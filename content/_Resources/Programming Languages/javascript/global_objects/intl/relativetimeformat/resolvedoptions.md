Intl.RelativeTimeFormat.prototype.resolvedOptions()
===================================================

 
The `resolvedOptions()` method of
[`Intl.RelativeTimeFormat`](../relativetimeformat) instances returns a
new object with properties reflecting the locale and relative time
formatting options computed during initialization of this
`Intl.RelativeTimeFormat` object.


 
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

 
A new object with properties reflecting the locale and number formatting
options computed during the initialization of the given
[`Intl.RelativeTimeFormat`](../relativetimeformat) object.



 
Description
-----------

 
The resulting object has the following properties:

[`locale`](#locale)

:   The BCP 47 language tag for the locale actually used. If any Unicode
    extension values were requested in the input BCP 47 language tag
    that led to this locale, the key-value pairs that were requested and
    are supported for this locale are included in `locale`.

[`style`](#style)

:   The length of the internationalized message. Possible values are:

    -   `"long"` (default, e.g., `in 1 month`)
    -   `"short"` (e.g., `in 1 mo.`),
    -   or `"narrow"` (e.g., `in 1 mo.`). The narrow style could be
        similar to the short style for some locales.

[`numeric`](#numeric)

:   The format of output message. Possible values are:

    -   `"always"` (default, e.g., `1 day ago`),
    -   or `"auto"` (e.g., `yesterday`). The `"auto"` value allows to
        not always have to use numeric values in the output.

[`numberingSystem`](#numberingsystem)

:   The value requested using the Unicode extension key `"nu"` or filled
    in as a default.



 
Examples
--------


 
### Using the resolvedOptions() method 

 
 
 
[js]


```js
const de = new Intl.RelativeTimeFormat("de-DE");
const usedOptions = de.resolvedOptions();

usedOptions.locale; // "de-DE"
usedOptions.style; // "long"
usedOptions.numeric; // "always"
usedOptions.numberingSystem; // "latn"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.relativetimeformat.prototype.resolvedoptions]](https://tc39.es/ecma402/#sec-intl.relativetimeformat.prototype.resolvedoptions)

  -------------------------------------------------------------------------------------------------------------------------------------------------


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

71

79

65

58

14

71

65

50

14

10.0

71

1.8

12.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `RelativeTimeFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/RelativeTimeFormat/RelativeTimeFormat)
for more details.

`numberingSystem`

73

79

70

60

14

73

79

52

14

11.0

73

1.8

12.0.0

 
See also 
--------

 
-   [`Intl.RelativeTimeFormat`](../relativetimeformat)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/RelativeTimeFormat/resolvedOptions>

