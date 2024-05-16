RegExp.prototype.flags
======================

 
The `flags` accessor property of [`RegExp`](../regexp) instances returns
the
[flags](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions#advanced_searching_with_flags)
of this regular expression.


 
Try it 
------

 



 
Description
-----------

 
`RegExp.prototype.flags` has a string as its value. Flags in the `flags`
property are sorted alphabetically (from left to right, e.g.
`"dgimsuvy"`). It actually invokes the other flag accessors
([`hasIndices`](hasindices), [`global`](global), etc.) one-by-one and
concatenates the results.

All built-in functions read the `flags` property instead of reading
individual flag accessors.

The set accessor of `flags` is `undefined`. You cannot change this
property directly.



 
Examples
--------


 
### Using flags 

 
 
 
[js]


```js
/foo/ig.flags; // "gi"
/bar/myu.flags; // "muy"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-regexp.prototype.flags]](https://tc39.es/ecma262/multipage/text-processing.html#sec-get-regexp.prototype.flags)

  ---------------------------------------------------------------------------------------------------------------------------------


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

`flags`

49

79

37

39

9

49

37

41

9

5.0

49

1.0

6.0.0

 
See also 
--------

 
-   [Polyfill of `RegExp.prototype.flags` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [Advanced searching with
    flags](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions#advanced_searching_with_flags)
    in the Regular expressions guide
-   [`RegExp.prototype.source`](source)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/flags>

