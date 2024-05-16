Intl.Segmenter() constructor
============================

 
The `Intl.Segmenter()` constructor creates
[`Intl.Segmenter`](../segmenter) objects.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Intl.Segmenter()
new Intl.Segmenter(locales)
new Intl.Segmenter(locales, options)
```


 
**Note:** `Intl.Segmenter()` can only be constructed with
[`new`](../../../operators/new). Attempting to call it without `new`
throws a [`TypeError`](../../typeerror).




 
### Parameters

 

[`locales`](#locales) [Optional]

:   A string with a BCP 47 language tag or an [`Intl.Locale`](../locale)
    instance, or an array of such locale identifiers. For the general
    form and interpretation of the `locales` argument, see [the
    parameter description on the `Intl` main
    page](../../intl#locales_argument).

[`options`](#options) [Optional]

:   An object containing the following properties, in the order they are
    retrieved (all of them are optional):

    [`localeMatcher`](#localematcher)

    :   The locale matching algorithm to use. Possible values are
        `"lookup"` and `"best fit"`; the default is `"best fit"`. For
        information about this option, see [Locale identification and
        negotiation](../../intl#locale_identification_and_negotiation).

    [`granularity`](#granularity)

    :   How granularly should the input be split. Possible values are:

        [`"grapheme"`](#grapheme) (default)

        :   Split the input into segments at grapheme cluster
            (user-perceived character) boundaries, as determined by the
            locale.

        [`"word"`](#word)

        :   Split the input into segments at word boundaries, as
            determined by the locale.

        [`"sentence"`](#sentence)

        :   Split the input into segments at sentence boundaries, as
            determined by the locale.



 
### Return value 

 
A new [`Intl.Segmenter`](../segmenter) instance.



 
### Exceptions

 

[`RangeError`](../../rangeerror)

:   Thrown if `locales` or `options` contain invalid values.



 
Examples
--------


 
### Basic usage 

 
The following example shows how to count words in a string using the
Japanese language (where splitting the string using `String` methods
would have given an incorrect result).

 
 
[js]


```js
const text = "吾輩は猫である。名前はたぬき。";
const japaneseSegmenter = new Intl.Segmenter("ja-JP", { granularity: "word" });
console.log(
  [...japaneseSegmenter.segment(text)].filter((segment) => segment.isWordLike)
    .length,
);
// 8, as the text is segmented as '吾輩'|'は'|'猫'|'で'|'ある'|'。'|'名前'|'は'|'たぬき'|'。'
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl-segmenter-constructor]](https://tc39.es/ecma402/#sec-intl-segmenter-constructor)

  ---------------------------------------------------------------------------------------------------


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

`Segmenter`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter/Segmenter>

