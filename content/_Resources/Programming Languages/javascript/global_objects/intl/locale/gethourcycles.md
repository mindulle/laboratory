Intl.Locale.prototype.getHourCycles()
=====================================

 
The `getHourCycles()` method of [`Intl.Locale`](../locale) instances
returns a list of one or more unique hour cycle identifiers for this
locale.

 
**Note:** In some versions of some browsers, this method was implemented
as an accessor property called `hourCycles`. However, because it returns
a new array on each access, it is now implemented as a method to prevent
the situation of `locale.hourCycles === locale.hourCycles` returning
`false`. Check the [browser compatibility table](#browser_compatibility)
for details.



 
Syntax
------

 
 
 
[js]


```js
getHourCycles()
```




 
### Parameters

 
None.



 
### Return value 

 
An array of strings representing all hour cycle types commonly used for
the `Locale`, sorted in descending preference. If the `Locale` already
has an [`hourCycle`](hourcycle), then the returned array contains that
single value.

Below is a list of supported hour cycle types.



 
### Supported hour cycle types 

 

[`h12`](#h12)

:   Hour system using 1--12; corresponds to \'h\' in patterns. The 12
    hour clock, with midnight starting at 12:00 am. As used, for
    example, in the United States.

[`h23`](#h23)

:   Hour system using 0--23; corresponds to \'H\' in patterns. The 24
    hour clock, with midnight starting at 0:00.

[`h11`](#h11)

:   Hour system using 0--11; corresponds to \'K\' in patterns. The 12
    hour clock, with midnight starting at 0:00 am. Mostly used in Japan.

[`h24`](#h24)

:   Hour system using 1--24; corresponds to \'k\' in pattern. The 24
    hour clock, with midnight starting at 24:00. Not used anywhere.



 
Examples
--------


 
### Obtaining supported hour cycles 

 
If the `Locale` object doesn\'t have a `hourCycle` already,
`getHourCycles()` lists all commonly-used collation types for the given
`Locale`. For examples of explicitly setting a `hourCycle`, see
[`hourCycle` examples](hourcycle#examples).

 
 
[js]


```js
const arEG = new Intl.Locale("ar-EG");
console.log(arEG.getHourCycles()); // ["h12"]
```


 
 
[js]


```js
const jaJP = new Intl.Locale("ja-JP");
console.log(jaJP.getHourCycles()); // ["h23"]
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------
  [Intl Locale Info Proposal\
  [\#
  sec-Intl.Locale.prototype.getHourCycles]](https://tc39.es/proposal-intl-locale-info/#sec-Intl.Locale.prototype.getHourCycles)

  ---------------------------------------------------------------------------------------------------------------------------------------


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

`getHourCycles`

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
-   [`Intl.Locale.prototype.hourCycle`](hourcycle)
-   [Unicode Hour Cycle
    Identifier](https://www.unicode.org/reports/tr35/#UnicodeHourCycleIdentifier)
    in the Unicode locale data markup language spec



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/getHourCycles>

