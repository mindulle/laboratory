SharedArrayBuffer.prototype.slice()
===================================

 
The `slice()` method of [`SharedArrayBuffer`](../sharedarraybuffer)
instances returns a new `SharedArrayBuffer` whose contents are a copy of
this `SharedArrayBuffer`\'s bytes from `start`, inclusive, up to `end`,
exclusive. If either `start` or `end` is negative, it refers to an index
from the end of the array, as opposed to from the beginning.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
slice()
slice(start)
slice(start, end)
```




 
### Parameters

 

[`start`](#start) [Optional]

:   Zero-based index at which to start extraction, [converted to an
    integer](../number#integer_conversion).

    -   Negative index counts back from the end of the buffer --- if
        `start < 0`, `start + buffer.length` is used.
    -   If `start < -buffer.length` or `start` is omitted, `0` is used.
    -   If `start >= buffer.length`, nothing is extracted.

[`end`](#end) [Optional]

:   Zero-based index at which to end extraction, [converted to an
    integer](../number#integer_conversion). `slice()` extracts up to but
    not including `end`.

    -   Negative index counts back from the end of the buffer --- if
        `end < 0`, `end + buffer.length` is used.
    -   If `end < -buffer.length`, `0` is used.
    -   If `end >= buffer.length` or `end` is omitted, `buffer.length`
        is used, causing all elements until the end to be extracted.
    -   If `end` is positioned before or at `start` after normalization,
        nothing is extracted.



 
### Return value 

 
A new [`SharedArrayBuffer`](../sharedarraybuffer) containing the
extracted elements.



 
Examples
--------


 
### Using slice() 

 
 
 
[js]


```js
const sab = new SharedArrayBuffer(1024);
sab.slice(); // SharedArrayBuffer { byteLength: 1024 }
sab.slice(2); // SharedArrayBuffer { byteLength: 1022 }
sab.slice(-2); // SharedArrayBuffer { byteLength: 2 }
sab.slice(0, 1); // SharedArrayBuffer { byteLength: 1 }
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-sharedarraybuffer.prototype.slice]](https://tc39.es/ecma262/multipage/structured-data.html#sec-sharedarraybuffer.prototype.slice)

  -----------------------------------------------------------------------------------------------------------------------------------------------


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

`slice`

68

79

79

55

15.2

89

79

63

15.2

15.0

No

1.0

8.10.0

 
See also 
--------

 
-   [`SharedArrayBuffer`](../sharedarraybuffer)
-   [`ArrayBuffer.prototype.slice()`](../arraybuffer/slice)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer/slice>

