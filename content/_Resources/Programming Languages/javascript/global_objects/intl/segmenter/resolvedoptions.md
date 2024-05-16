Intl.Segmenter.prototype.resolvedOptions()
==========================================

 
The `resolvedOptions()` method of [`Intl.Segmenter`](../segmenter)
instances returns a new object with properties reflecting the locale and
granularity options computed during the initialization of this
`Intl.Segmenter` object.


 
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

 
A new object with properties reflecting the locale and collation options
computed during the initialization of the given
[`Intl.Segmenter`](../segmenter) object.



 
Description
-----------

 
The resulting object has the following properties:

[`locale`](#locale)

:   The BCP 47 language tag for the locale actually used. If any Unicode
    extension values were requested in the input BCP 47 language tag
    that led to this locale, the key-value pairs that were requested and
    are supported for this locale are included in `locale`.

[`granularity`](#granularity)

:   The value provided for this property in the `options` argument or
    filled in as the default.



 
Examples
--------


 
### Basic usage 

 
 
 
[js]


```js
const spanishSegmenter = new Intl.Segmenter("es", { granularity: "sentence" });
const options = spanishSegmenter.resolvedOptions();
console.log(options.locale); // "es"
console.log(options.granularity); // "sentence"
```




 
### Default granularity 

 
 
 
[js]


```js
const spanishSegmenter = new Intl.Segmenter("es");
const options = spanishSegmenter.resolvedOptions();
console.log(options.locale); // "es"
console.log(options.granularity); // "grapheme"
```




 
### Fallback locale 

 
 
 
[js]


```js
const banSegmenter = new Intl.Segmenter("ban");
const options = banSegmenter.resolvedOptions();
console.log(options.locale);
// "fr" on a runtime where the Balinese locale
// is not supported and French is the default locale
console.log(options.granularity); // "grapheme"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.segmenter.prototype.resolvedoptions]](https://tc39.es/ecma402/#sec-intl.segmenter.prototype.resolvedoptions)

  -------------------------------------------------------------------------------------------------------------------------------


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

87

87

preview

73

14.1

87

No

62

14.5

14.0

87

1.8

16.0.0

 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter/resolvedOptions>

