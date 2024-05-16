Intl.Locale.prototype.getTextInfo()
===================================

 
The `getTextInfo()` method of [`Intl.Locale`](../locale) instances
returns the ordering of characters indicated by either `ltr`
(left-to-right) or by `rtl` (right-to-left) for this locale.

 
**Note:** In some versions of some browsers, this method was implemented
as an accessor property called `textInfo`. However, because it returns a
new object on each access, it is now implemented as a method to prevent
the situation of `locale.textInfo === locale.textInfo` returning
`false`. Check the [browser compatibility table](#browser_compatibility)
for details.



 
Syntax
------

 
 
 
[js]


```js
getTextInfo()
```




 
### Parameters

 
None.



 
### Return value 

 
An object representing text typesetting information associated with the
Locale data specified in [UTS 35\'s Layouts
Elements](https://www.unicode.org/reports/tr35/tr35-general.html#Layout_Elements).
It has the following properties:

[`direction`](#direction)

:   A string indicating the direction of text for the locale. Can be
    either `"ltr"` (left-to-right) or `"rtl"` (right-to-left).



 
Examples
--------


 
### Obtaining text info 

 
Return the supported text directions for a given `Locale`.

 
 
[js]


```js
const ar = new Intl.Locale("ar");
console.log(ar.getTextInfo()); // { direction: "rtl" }
console.log(ar.getTextInfo().direction); // "rtl"
```


 
 
[js]


```js
const es = new Intl.Locale("es");
console.log(es.getTextInfo()); // { direction: "ltr" }
console.log(es.getTextInfo().direction); // "ltr"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [Intl Locale Info Proposal\
  [\#
  sec-Intl.Locale.prototype.getTextInfo]](https://tc39.es/proposal-intl-locale-info/#sec-Intl.Locale.prototype.getTextInfo)

  -----------------------------------------------------------------------------------------------------------------------------------


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

`getTextInfo`

99Implemented as an accessor property.

99Implemented as an accessor property.

No

85Implemented as an accessor property.

17

15.4--previewImplemented as an accessor property.

99Implemented as an accessor property.

No

68Implemented as an accessor property.

17

15.4Implemented as an accessor property.

18.0Implemented as an accessor property.

99Implemented as an accessor property.

1.19

18.0.0Implemented as an accessor property.

 
See also 
--------

 
-   [`Intl.Locale`](../locale)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/getTextInfo>

