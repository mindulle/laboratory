Error: fileName
===============

 
 
**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.


The `fileName` data property of an [`Error`](../error) instance contains
the path to the file that raised this error.


 
Value
-----

 
A string.

 
Property attributes of `Error: fileName`




Writable

yes

Enumerable

no

Configurable

yes

 
Description
-----------

 
This non-standard property contains the path to the file that raised
this error. If called from a debugger context, the Firefox Developer
Tools for example, \"debugger eval code\" is returned.



 
Examples
--------


 
### Using fileName 

 
 
 
[js]


```js
const e = new Error("Could not parse input");
throw e;
// e.fileName could look like "file:///C:/example.html"
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

`fileName`

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
-   [`Error.prototype.columnNumber`](columnnumber)
-   [`Error.prototype.lineNumber`](linenumber)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/fileName>

