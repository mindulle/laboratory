Intl.Locale.prototype.getCollations()
=====================================

 
The `getCollations()` method of [`Intl.Locale`](../locale) instances
returns a list of one or more [collation
types](https://www.unicode.org/reports/tr35/tr35-collation.html#CLDR_collation)
for this locale.

 
**Note:** In some versions of some browsers, this method was implemented
as an accessor property called `collations`. However, because it returns
a new array on each access, it is now implemented as a method to prevent
the situation of `locale.collations === locale.collations` returning
`false`. Check the [browser compatibility table](#browser_compatibility)
for details.



 
Syntax
------

 
 
 
[js]


```js
getCollations()
```




 
### Parameters

 
None.



 
### Return value 

 
An array of strings representing all collation types commonly used for
the `Locale`, sorted in alphabetical order, with the `standard` and
`search` values always excluded. If the `Locale` already has a
[`collation`](collation), then the returned array contains that single
value.

Below is a list of the supported collation types, adapted from the
[Unicode collation
specification](https://github.com/unicode-org/cldr/blob/2dd06669d833823e26872f249aa304bc9d9d2a90/common/bcp47/collation.xml).



 
### Supported collation types 

 

[`big5han`](#big5han)

:   Pinyin ordering for Latin, big5 charset ordering for CJK characters
    (for Chinese)

     
    **Warning:** The `big5han` collation type is deprecated, not
    available in Firefox, Chrome or Edge.
    

[`compat`](#compat)

:   A previous version of the ordering, for compatibility (for Arabic)

[`dict`](#dict)

:   Dictionary style ordering (for Sinhala)

[`direct`](#direct)

:   Binary code point order

     
    **Warning:** The `direct` collation type has been deprecated. Do not
    use.
    

[`ducet`](#ducet)

:   The default Unicode collation element table order

     
    **Warning:** The `ducet` collation type is not available to the Web.
    Use the `und` locale without a collation type specifier instead.
    `und` is the collation that is the closest to `ducet`.
    

[`emoji`](#emoji)

:   Recommended ordering for emoji characters (for the `und` locale)

[`eor`](#eor)

:   European ordering rules (for the `und` locale)

[`gb2312`](#gb2312)

:   Pinyin ordering for Latin, gb2312han charset ordering for CJK
    characters (for Chinese)

     
    **Warning:** The `gb2312` collation type is deprecated, not
    available in Firefox, Chrome or Edge.
    

[`phonebk`](#phonebk)

:   Phonebook style ordering (for German)

[`phonetic`](#phonetic)

:   Phonetic ordering (sorting based on pronunciation; for Lingala)

[`pinyin`](#pinyin)

:   Pinyin ordering for Latin and for CJK characters (for Chinese)

[`reformed`](#reformed)

:   Reformed ordering (formerly for Swedish)

     
    **Warning:** Do not use explicitly. This is the old name for the
    default ordering for Swedish [whose collation naming used to differ
    from other
    languages](https://unicode-org.atlassian.net/browse/CLDR-15603).
    Since this was the default, request `sv` instead of requesting
    `sv-u-co-reformed`.
    

[`search`](#search)

:   Special collation type for string search

     
    **Warning:** Do not use as a collation type, since in
    [`Intl.Collator`](../collator), this collation is activated via the
    `"search"` value for the `usage` option. There is currently no API
    for substring search, so this is currently only good for filtering a
    list of strings by trying a full-string match of the key against
    each list item.
    

[`searchjl`](#searchjl)

:   Special collation type for Korean initial consonant search

     
    **Warning:** This collation is not for sorting, even though it is
    made available through [`Intl.Collator`](../collator) instantiated
    with usage `"sort"` as opposed to usage `"search"`.
    

[`standard`](#standard)

:   Default ordering for each language, except Chinese (and, previously,
    Swedish)

     
    **Warning:** Do not use explicitly. In general, it\'s unnecessary to
    specify this explicitly and specifying this for Swedish is
    problematic due to the different meaning for Swedish in the past.
    

[`stroke`](#stroke)

:   Pinyin ordering for Latin, stroke order for CJK characters (for
    Chinese)

[`trad`](#trad)

:   Traditional style ordering (such as in Spanish)

[`unihan`](#unihan)

:   Radical-stroke ordering for Han characters (for Chinese, Japanese,
    and Korean). Pinyin ordering for Latin in the case of Chinese.

     
    **Note:** The `unihan` collation type is not available in Chrome or
    Edge.
    

[`zhuyin`](#zhuyin)

:   Pinyin ordering for Latin, zhuyin order for Bopomofo and CJK
    characters (for Chinese)



 
Examples
--------


 
### Obtaining supported collation types 

 
If the `Locale` object doesn\'t have a `collation` already,
`getCollations()` lists all commonly-used collation types for the given
`Locale`. For examples of explicitly setting a `collation`, see
[`collation` examples](collation#examples).

 
 
[js]


```js
const locale = new Intl.Locale("zh");
console.log(locale.getCollations()); // ["pinyin", "stroke", "zhuyin", "emoji", "eor"]
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------
  [Intl Locale Info Proposal\
  [\#
  sec-Intl.Locale.prototype.getCollations]](https://tc39.es/proposal-intl-locale-info/#sec-Intl.Locale.prototype.getCollations)

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

`getCollations`

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
-   [`Intl.Locale.prototype.collation`](collation)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale/getCollations>

