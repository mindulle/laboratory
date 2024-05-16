Intl.Locale.prototype.getTimeZones()
====================================

 
The `getTimeZones()` method of [`Intl.Locale`](../locale) instances
returns a list of supported time zones for this locale.

 
**Note:** In some versions of some browsers, this method was implemented
as an accessor property called `timeZones`. However, because it returns
a new array on each access, it is now implemented as a method to prevent
the situation of `locale.timeZones === locale.timeZones` returning
`false`. Check the [browser compatibility table](#browser_compatibility)
for details.



 
Syntax
------

 
 
 
[js]


```js
getTimeZones()
```




 
### Parameters

 
None.



 
### Return value 

 
An array of strings representing supported time zones for the associated
`Locale`, where each value is an [IANA time zone canonical
name](https://en.wikipedia.org/wiki/Daylight_saving_time#IANA_time_zone_database),
sorted in alphabetical order. If the locale identifier does not contain
a region subtag, the returned value is `undefined`.



 
Examples
--------


 
### Obtaining supported time zones 

 
List supported time zones for a given `Locale`.

 
 
[js]


```js
const arEG = new Intl.Locale("ar-EG");
console.log(arEG.getTimeZones()); // ["Africa/Cairo"]
```


 
 
[js]


```js
const jaJP = new Intl.Locale("ja-JP");
console.log(jaJP.getTimeZones()); // ["Asia/Tokyo"]
```


 
 
[js]


```js
const ar = new Intl.Locale("ar");
console.log(ar.getTimeZones()); // undefined
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [Intl Locale Info Proposal\
  [\#
  sec-Intl.Locale.prototype.getTimeZones]](https://tc39.es/proposal-intl-locale-info/#sec-Intl.Locale.prototype.getTimeZones)

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

`getTimeZones`

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
-   [IANA time zone
    database](https://en.wikipedia.org/wiki/Daylight_saving_time#IANA_time_zone_database)
    on Wikipedia



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/getTimeZones>

