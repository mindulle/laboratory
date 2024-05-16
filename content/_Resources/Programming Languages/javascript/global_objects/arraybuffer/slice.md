ArrayBuffer.prototype.slice()
=============================


The `slice()` method of [`ArrayBuffer`](../arraybuffer) instances
returns a new `ArrayBuffer` whose contents are a copy of this
`ArrayBuffer`\'s bytes from `start`, inclusive, up to `end`, exclusive.
If either `start` or `end` is negative, it refers to an index from the
end of the array, as opposed to from the beginning.



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


A new [`ArrayBuffer`](../arraybuffer) containing the extracted elements.




Examples
--------



### Copying an ArrayBuffer 




[js]


```js
const buf1 = new ArrayBuffer(8);
const buf2 = buf1.slice(0);
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-arraybuffer.prototype.slice]](https://tc39.es/ecma262/multipage/structured-data.html#sec-arraybuffer.prototype.slice)

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

`slice`

17

12

12The non-standard `ArrayBuffer.slice()` method has been removed in
Firefox 53 (but the standardized version `ArrayBuffer.prototype.slice()`
is kept.

12.1

5.1

18

14The non-standard `ArrayBuffer.slice()` method has been removed in
Firefox 53 (but the standardized version `ArrayBuffer.prototype.slice()`
is kept.

12.1

6

1.0

4.4

1.0

0.12.0


See also 
--------


-   [`ArrayBuffer`](../arraybuffer)
-   [`SharedArrayBuffer.prototype.slice()`](../sharedarraybuffer/slice)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/slice>

