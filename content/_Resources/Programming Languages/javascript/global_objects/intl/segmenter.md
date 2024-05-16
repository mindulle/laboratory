Intl.Segmenter
==============

 
The `Intl.Segmenter` object enables locale-sensitive text segmentation,
enabling you to get meaningful items (graphemes, words or sentences)
from a string.


 
Try it 
------

 



 
Constructor
-----------

 

[`Intl.Segmenter()`](segmenter/segmenter)

:   Creates a new `Intl.Segmenter` object.



 
Static methods 
--------------

 

[`Intl.Segmenter.supportedLocalesOf()`](segmenter/supportedlocalesof)

:   Returns an array containing those of the provided locales that are
    supported without having to fall back to the runtime\'s default
    locale.



 
Instance properties 
-------------------

 
These properties are defined on `Intl.Segmenter.prototype` and shared by
all `Intl.Segmenter` instances.

[`Intl.Segmenter.prototype.constructor`](../object/constructor)

:   The constructor function that created the instance object. For
    `Intl.Segmenter` instances, the initial value is the
    [`Intl.Segmenter`](segmenter/segmenter) constructor.

[`Intl.Segmenter.prototype[@@toStringTag]`](#intl.segmenter.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](../symbol/tostringtag)
    property is the string `"Intl.Segmenter"`. This property is used in
    [`Object.prototype.toString()`](../object/tostring).



 
Instance methods 
----------------

 

[`Intl.Segmenter.prototype.resolvedOptions()`](segmenter/resolvedoptions)

:   Returns a new object with properties reflecting the locale and
    granularity options computed during initialization of this
    `Intl.Segmenter` object.

[`Intl.Segmenter.prototype.segment()`](segmenter/segment)

:   Returns a new iterable [`Segments`](segmenter/segment/segments)
    instance representing the segments of a string according to the
    locale and granularity of this `Intl.Segmenter` instance.



 
Examples
--------


 
### Basic usage and difference from String.prototype.split() 

 
If we were to use [`String.prototype.split(" ")`](../string/split) to
segment a text in words, we would not get the correct result if the
locale of the text does not use whitespaces between words (which is the
case for Japanese, Chinese, Thai, Lao, Khmer, Myanmar, etc.).

 
 
[js]


```js
const str = "吾輩は猫である。名前はたぬき。";
console.table(str.split(" "));
// ['吾輩は猫である。名前はたぬき。']
// The two sentences are not correctly segmented.
```


 
 
[js]


```js
const str = "吾輩は猫である。名前はたぬき。";
const segmenterJa = new Intl.Segmenter("ja-JP", { granularity: "word" });

const segments = segmenterJa.segment(str);
console.table(Array.from(segments));
// [{segment: '吾輩', index: 0, input: '吾輩は猫である。名前はたぬき。', isWordLike: true},
// etc.
// ]
```




Specifications
--------------

 
  -------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  segmenter-objects]](https://tc39.es/ecma402/#segmenter-objects)

  -------------------------------------------------------------------------


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

`segment`

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

`supportedLocalesOf`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter>

