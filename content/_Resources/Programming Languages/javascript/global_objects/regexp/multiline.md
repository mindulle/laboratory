RegExp.prototype.multiline
==========================

 
The `multiline` accessor property of [`RegExp`](../regexp) instances
returns whether or not the `m` flag is used with this regular
expression.


 
Try it 
------

 



 
Description
-----------

 
`RegExp.prototype.multiline` has the value `true` if the `m` flag was
used; otherwise, `false`. The `m` flag indicates that a multiline input
string should be treated as multiple lines. For example, if `m` is used,
`^` and `$` change from matching at only the start or end of the entire
string to the start or end of any line within the string.

The set accessor of `multiline` is `undefined`. You cannot change this
property directly.



 
Examples
--------


 
### Using multiline 

 
 
 
[js]


```js
const regex = /foo/m;

console.log(regex.multiline); // true
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-regexp.prototype.multiline]](https://tc39.es/ecma262/multipage/text-processing.html#sec-get-regexp.prototype.multiline)

  -----------------------------------------------------------------------------------------------------------------------------------------


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

`multiline`

1

12

1

5

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`prototype_accessor`

48

12

38

35

1.3

48

38

35

1

5.0

48

1.0

6.0.0

 
See also 
--------

 
-   [`RegExp.prototype.lastIndex`](lastindex)
-   [`RegExp.prototype.dotAll`](dotall)
-   [`RegExp.prototype.global`](global)
-   [`RegExp.prototype.hasIndices`](hasindices)
-   [`RegExp.prototype.ignoreCase`](ignorecase)
-   [`RegExp.prototype.source`](source)
-   [`RegExp.prototype.sticky`](sticky)
-   [`RegExp.prototype.unicode`](unicode)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/multiline>

