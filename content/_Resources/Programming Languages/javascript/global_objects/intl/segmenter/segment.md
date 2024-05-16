Intl.Segmenter.prototype.segment()
==================================

 
The `segment()` method of [`Intl.Segmenter`](../segmenter) instances
segments a string according to the locale and granularity of this
`Intl.Segmenter` object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
segment(input)
```




 
### Parameters

 

[`input`](#input)

:   The text to be segmented as a string.



 
### Return value 

 
A new iterable [`Segments`](segment/segments) object containing the
segments of the input string, using the segmenter\'s locale and
granularity.



 
Examples
--------

 
 
 
[js]


```js
// Create a locale-specific word segmenter
const segmenter = new Intl.Segmenter("fr", { granularity: "word" });

// Use it to get an iterator over the segments of a string
const input = "Moi ? N'est-ce pas ?";
const segments = segmenter.segment(input);

// Use that for segmentation
for (const { segment, index, isWordLike } of segments) {
  console.log(
    "segment at code units [%d, %d]: «%s»%s",
    index,
    index + segment.length,
    segment,
    isWordLike ? " (word-like)" : "",
  );
}
// segment at code units [0, 3]: «Moi» (word-like)
// segment at code units [3, 4]: « »
// segment at code units [4, 5]: «?»
// segment at code units [5, 6]: « »
// segment at code units [6, 11]: «N'est» (word-like)
// segment at code units [11, 12]: «-»
// segment at code units [12, 14]: «ce» (word-like)
// segment at code units [14, 15]: « »
// segment at code units [15, 18]: «pas» (word-like)
// segment at code units [18, 19]: « »
// segment at code units [19, 20]: «?»
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-intl.segmenter.prototype.segment]](https://tc39.es/ecma402/#sec-intl.segmenter.prototype.segment)

  ---------------------------------------------------------------------------------------------------------------


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

 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter/segment>

