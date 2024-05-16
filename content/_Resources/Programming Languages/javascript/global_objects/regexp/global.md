RegExp.prototype.global
=======================

 
The `global` accessor property of [`RegExp`](../regexp) instances
returns whether or not the `g` flag is used with this regular
expression.


 
Try it 
------

 



 
Description
-----------

 
`RegExp.prototype.global` has the value `true` if the `g` flag was used;
otherwise, `false`. The `g` flag indicates that the regular expression
should be tested against all possible matches in a string. Each call to
[`exec()`](exec) will update its [`lastIndex`](lastindex) property, so
that the next call to `exec()` will start at the next character.

Some methods, such as
[`String.prototype.matchAll()`](../string/matchall) and
[`String.prototype.replaceAll()`](../string/replaceall), will validate
that, if the parameter is a regex, it is global. The regex\'s
[`@@match`](@@match) and [`@@replace`](@@replace) methods (called by
[`String.prototype.match()`](../string/match) and
[`String.prototype.replace()`](../string/replace)) would also have
different behaviors when the regex is global.

The set accessor of `global` is `undefined`. You cannot change this
property directly.



 
Examples
--------


 
### Using global 

 
 
 
[js]


```js
const regex = /foo/g;
console.log(regex.global); // true

const str = "fooexamplefoo";
const str1 = str.replace(regex, "");
console.log(str1); // example

const regex1 = /foo/;
const str2 = str.replace(regex1, "");
console.log(str2); // examplefoo
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-regexp.prototype.global]](https://tc39.es/ecma262/multipage/text-processing.html#sec-get-regexp.prototype.global)

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

`global`

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
-   [`RegExp.prototype.hasIndices`](hasindices)
-   [`RegExp.prototype.ignoreCase`](ignorecase)
-   [`RegExp.prototype.multiline`](multiline)
-   [`RegExp.prototype.source`](source)
-   [`RegExp.prototype.sticky`](sticky)
-   [`RegExp.prototype.unicode`](unicode)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/global>

