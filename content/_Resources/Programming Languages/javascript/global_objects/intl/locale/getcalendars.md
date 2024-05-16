Intl.Locale.prototype.getCalendars()
====================================

 
The `getCalendars()` method of [`Intl.Locale`](../locale) instances
returns a list of one or more unique calendar identifiers for this
locale.

 
**Note:** In some versions of some browsers, this method was implemented
as an accessor property called `calendars`. However, because it returns
a new array on each access, it is now implemented as a method to prevent
the situation of `locale.calendars === locale.calendars` returning
`false`. Check the [browser compatibility table](#browser_compatibility)
for details.



 
Syntax
------

 
 
 
[js]


```js
getCalendars()
```




 
### Parameters

 
None.



 
### Return value 

 
An array of strings representing all calendars commonly used for the
`Locale`, sorted in descending preference. If the `Locale` already has a
[`calendar`](calendar), then the returned array contains that single
value.

Below is a list of the supported calendar era types.



 
### Supported calendar types 

 

[`buddhist`](#buddhist)

:   Thai Buddhist calendar

[`chinese`](#chinese)

:   Traditional Chinese calendar

[`coptic`](#coptic)

:   Coptic calendar

[`dangi`](#dangi)

:   Traditional Korean calendar

[`ethioaa`](#ethioaa)

:   Ethiopic calendar, Amete Alem (epoch approx. 5493 B.C.E)

[`ethiopic`](#ethiopic)

:   Ethiopic calendar, Amete Mihret (epoch approx, 8 C.E.)

[`gregory`](#gregory)

:   Gregorian calendar

[`hebrew`](#hebrew)

:   Traditional Hebrew calendar

[`indian`](#indian)

:   Indian calendar

[`islamic`](#islamic)

:   Islamic calendar

[`islamic-umalqura`](#islamic-umalqura)

:   Islamic calendar, Umm al-Qura

[`islamic-tbla`](#islamic-tbla)

:   Islamic calendar, tabular (intercalary years
    \[2,5,7,10,13,16,18,21,24,26,29\] - astronomical epoch)

[`islamic-civil`](#islamic-civil)

:   Islamic calendar, tabular (intercalary years
    \[2,5,7,10,13,16,18,21,24,26,29\] - civil epoch)

[`islamic-rgsa`](#islamic-rgsa)

:   Islamic calendar, Saudi Arabia sighting

[`iso8601`](#iso8601)

:   ISO calendar (Gregorian calendar using the ISO 8601 calendar week
    rules)

[`japanese`](#japanese)

:   Japanese Imperial calendar

[`persian`](#persian)

:   Persian calendar

[`roc`](#roc)

:   Civil (algorithmic) Arabic calendar

[`islamicc`](#islamicc)

:   Civil (algorithmic) Arabic calendar

     
    **Warning:** The `islamicc` calendar key has been deprecated. Please
    use `islamic-civil`.
    



 
Examples
--------


 
### Obtaining supported calendars 

 
If the `Locale` object doesn\'t have a `calendar` already,
`getCalendars()` lists all commonly-used calendars for the given
`Locale`. For examples of explicitly setting a `calendar`, see
[`calendar` examples](calendar#examples).

 
 
[js]


```js
const arEG = new Intl.Locale("ar-EG");
console.log(arEG.getCalendars()); // ["gregory", "coptic", "islamic", "islamic-civil", "islamic-tbla"]
```


 
 
[js]


```js
const jaJP = new Intl.Locale("ja-JP");
console.log(jaJP.getCalendars()); // ["gregory", "japanese"]
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [Intl Locale Info Proposal\
  [\#
  sec-Intl.Locale.prototype.getCalendars]](https://tc39.es/proposal-intl-locale-info/#sec-Intl.Locale.prototype.getCalendars)

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

`getCalendars`

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
-   [`Intl.Locale.prototype.calendar`](calendar)
-   [Unicode Calendar
    Identifier](https://www.unicode.org/reports/tr35/#UnicodeCalendarIdentifier)
    in the Unicode locale data markup language spec



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/getCalendars>

