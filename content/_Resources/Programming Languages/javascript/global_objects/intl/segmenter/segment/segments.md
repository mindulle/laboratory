Segments
========

 
A `Segments` object is an iterable collection of the segments of a text
string. It is returned by a call to the [`segment()`](../segment) method
of an [`Intl.Segmenter`](../../segmenter) object.


 
Try it 
------

 



 
Instance methods 
----------------

 

[`Segments.prototype.containing()`](segments/containing)

:   Returns an object describing the segment in the original string that
    includes the code unit at a specified index.

[`Segments.prototype[@@iterator]()`](segments/@@iterator)

:   Returns an iterator to iterate over the segments.



Specifications
--------------

 
  -------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-segments-objects]](https://tc39.es/ecma402/#sec-segments-objects)

  -------------------------------------------------------------------------------


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

`@@iterator`

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

`Segments`

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

 
-   [`Intl.Segmenter`](../../segmenter)
-   [`Intl.Segmenter.prototype.segment()`](../segment)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter/segment/Segments>

