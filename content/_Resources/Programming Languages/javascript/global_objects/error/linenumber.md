Error: lineNumber
=================

 
 
**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.


The `lineNumber` data property of an [`Error`](../error) instance
contains the line number in the file that raised this error.


 
Value
-----

 
A positive integer.

 
Property attributes of `Error: lineNumber`




Writable

yes

Enumerable

no

Configurable

yes

 
Examples
--------


 
### Using lineNumber 

 
 
 
[js]


```js
try {
  throw new Error("Could not parse input");
} catch (err) {
  console.log(err.lineNumber); // 2
}
```




 
### Alternative example using error event 

 
 
 
[js]


```js
window.addEventListener("error", (e) => {
  console.log(e.lineNumber); // 5
});
const e = new Error("Could not parse input");
throw e;
```


This is not a standard feature and lacks widespread support. See the
browser compatibility table below.



 
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

`lineNumber`

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
-   [`Error.prototype.fileName`](filename)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/lineNumber>

