Intl.Locale.prototype.getWeekInfo()
===================================

 
The `getWeekInfo()` method of [`Intl.Locale`](../locale) instances
returns a `weekInfo` object with the properties `firstDay`, `weekend`
and `minimalDays` for this locale.

 
**Note:** In some versions of some browsers, this method was implemented
as an accessor property called `weekInfo`. However, because it returns a
new object on each access, it is now implemented as a method to prevent
the situation of `locale.weekInfo === locale.weekInfo` returning
`false`. Check the [browser compatibility table](#browser_compatibility)
for details.



 
Syntax
------

 
 
 
[js]


```js
getWeekInfo()
```




 
### Parameters

 
None.



 
### Return value 

 
An object representing week information associated with the Locale data
specified in [UTS 35\'s Week
Elements](https://www.unicode.org/reports/tr35/tr35-dates.html#Date_Patterns_Week_Elements).
It has the following properties:

[`firstDay`](#firstday)

:   An integer indicating the first day of the week for the locale. Can
    be either `1` (Monday) or `7` (Sunday).

[`weekend`](#weekend)

:   An array of integers indicating the weekend days for the locale,
    where `1` is Monday and `7` is Sunday.

[`minimalDays`](#minimaldays)

:   An integer between 1 and 7 indicating the minimal days required in
    the first week of a month or year, for calendar purposes.



 
Examples
--------


 
### Obtaining the Week Information 

 
Return the week information for a given `Locale`.

 
 
[js]


```js
const he = new Intl.Locale("he");
console.log(he.getWeekInfo()); // { firstDay: 7, weekend: [5, 6], minimalDays: 1 }

const af = new Intl.Locale("af");
console.log(af.getWeekInfo()); // { firstDay: 7, weekend: [6, 7], minimalDays: 1 }

const enGB = new Intl.Locale("en-GB");
console.log(enGB.getWeekInfo()); // { firstDay: 1, weekend: [6, 7], minimalDays: 4 }

const msBN = new Intl.Locale("ms-BN");
console.log(msBN.getWeekInfo()); // { firstDay: 7, weekend: [5, 7], minimalDays: 1 }
// Brunei weekend is Friday and Sunday but not Saturday
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [Intl Locale Info Proposal\
  [\#
  sec-Intl.Locale.prototype.getWeekInfo]](https://tc39.es/proposal-intl-locale-info/#sec-Intl.Locale.prototype.getWeekInfo)

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

`getWeekInfo`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/getWeekInfo>

