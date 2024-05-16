Error: columnNumber
===================

 
 
**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.


The `columnNumber` data property of an [`Error`](../error) instance
contains the column number in the line of the file that raised this
error.


 
Value
-----

 
A positive integer.

 
Property attributes of `Error: columnNumber`




Writable

yes

Enumerable

no

Configurable

yes

 
Examples
--------


 
### Using columnNumber 

 
 
 
[js]


```js
try {
  throw new Error("Could not parse input");
} catch (err) {
  console.log(err.columnNumber); // 9
}
```




 
Specifications
--------------

 
Not part of any standard.



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

`columnNumber`

No

No

1

No

No

No

4

No

No

No

No

No

No

 
See also 
--------

 
-   [`Error.prototype.stack`](stack)
-   [`Error.prototype.lineNumber`](linenumber)
-   [`Error.prototype.fileName`](filename)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/columnNumber>

