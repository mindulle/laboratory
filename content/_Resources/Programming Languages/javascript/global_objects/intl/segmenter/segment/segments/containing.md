Segments.prototype.containing()
===============================

 
The `containing()` method of [`Segments`](../segments) instances returns
an object describing the segment in the string that includes the code
unit at the specified index.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
containing(codeUnitIndex)
```




 
### Parameters

 

[`codeUnitIndex`](#codeunitindex) [Optional]

:   A number specifying the index of the code unit in the original input
    string. If the value is omitted, it defaults to `0`.



 
### Return value 

 
An object describing the segment of the original string with the
following properties, or `undefined` if the supplied index value is out
of bounds.

[`segment`](#segment)

:   A string containing the segment extracted from the original input
    string.

[`index`](#index)

:   The code unit index in the original input string at which the
    segment begins.

[`input`](#input)

:   The complete input string that was segmented.

[`isWordLike`](#iswordlike)

:   A boolean value only if `granularity` is `"word"`; otherwise,
    `undefined`. If `granularity` is `"word"`, then `isWordLike` is
    `true` when the segment is word-like (i.e., consists of
    letters/numbers/ideographs/etc.); otherwise, `false`.



 
Examples
--------

 
 
 
[js]


```js
// ┃0 1 2 3 4 5┃6┃7┃8┃9  ← code unit index
// ┃A l l o n s┃-┃y┃!┃   ← code unit
const input = "Allons-y!";

const segmenter = new Intl.Segmenter("fr", { granularity: "word" });
const segments = segmenter.segment(input);

let current = segments.containing();
// { index: 0, segment: "Allons", isWordLike: true }

current = segments.containing(4);
// { index: 0, segment: "Allons", isWordLike: true }

current = segments.containing(6);
// { index: 6, segment: "-", isWordLike: false }

current = segments.containing(current.index + current.segment.length);
// { index: 7, segment: "y", isWordLike: true }

current = segments.containing(current.index + current.segment.length);
// { index: 8, segment: "!", isWordLike: false }

current = segments.containing(current.index + current.segment.length);
// undefined
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\# sec-%segmentsprototype%.containing]](#)

  -----------------------------------------------------------------------


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

`containing`

87

87

No

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

 
See also 
--------

 
-   [`Intl.Segmenter`](../../../segmenter)
-   [`Intl.Segmenter.prototype.segment()`](../../segment)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter/segment/Segments/containing>

