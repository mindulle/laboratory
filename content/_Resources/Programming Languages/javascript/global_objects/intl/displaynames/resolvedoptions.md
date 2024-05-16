Intl.DisplayNames.prototype.resolvedOptions()
=============================================

 
The `resolvedOptions()` method of [`Intl.DisplayNames`](../displaynames)
instances returns a new object with properties reflecting the locale and
style formatting options computed during the construction of this
`Intl.DisplayNames` object.


 
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
[`Intl.DisplayNames`](../displaynames) object.



 
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
    the constructor or the default value (`"language"`). Its value is
    either `"language"`, `"region"`, `"script"`, or `"currency"`.

[`fallback`](#fallback)

:   The value provided for this property in the options argument of the
    constructor or the default value (`"code"`). Its value is either
    `"code"` or `"none"`.



 
Examples
--------


 
### Using resolvedOptions 

 
 
 
[js]


```js
const displayNames = new Intl.DisplayNames(["de-DE"], { type: "region" });

const usedOptions = displayNames.resolvedOptions();
console.log(usedOptions.locale); // "de-DE"
console.log(usedOptions.style); // "long"
console.log(usedOptions.type); // "region"
console.log(usedOptions.fallback); // "code"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.DisplayNames.prototype.resolvedOptions]](https://tc39.es/ecma402/#sec-Intl.DisplayNames.prototype.resolvedOptions)

  -------------------------------------------------------------------------------------------------------------------------------------


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

81

81

86

68

14.1

81

86

58

14.5

13.0

81

1.8

14.0.0

 
See also 
--------

 
-   [`Intl.DisplayNames`](../displaynames)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DisplayNames/resolvedOptions>

