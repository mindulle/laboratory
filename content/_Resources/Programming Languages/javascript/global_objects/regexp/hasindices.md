RegExp.prototype.hasIndices
===========================

 
The `hasIndices` accessor property of [`RegExp`](../regexp) instances
returns whether or not the `d` flag is used with this regular
expression.


 
Try it 
------

 



 
Description
-----------

 
`RegExp.prototype.hasIndices` has the value `true` if the `d` flag was
used; otherwise, `false`. The `d` flag indicates that the result of a
regular expression match should contain the start and end indices of the
substrings of each capture group. It does not change the regex\'s
interpretation or matching behavior in any way, but only provides
additional information in the matching result.

This flag primarily affects the return value of [`exec()`](exec). If the
`d` flag is present, the array returned by `exec()` has an additional
`indices` property as described in the `exec()` method\'s [return
value](exec#return_value). Because all other regex-related methods (such
as [`String.prototype.match()`](../string/match)) call `exec()`
internally, they will also return the indices if the regex has the `d`
flag.

The set accessor of `hasIndices` is `undefined`. You cannot change this
property directly.



 
Examples
--------

 
There\'s a more detailed usage example at [Groups and backreferences \>
Using groups and match
indices](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions/Groups_and_backreferences#using_groups_and_match_indices).



 
### Using hasIndices 

 
 
 
[js]


```js
const str1 = "foo bar foo";

const regex1 = /foo/dg;

console.log(regex1.hasIndices); // true

console.log(regex1.exec(str1).indices[0]); // [0, 3]
console.log(regex1.exec(str1).indices[0]); // [8, 11]

const str2 = "foo bar foo";

const regex2 = /foo/;

console.log(regex2.hasIndices); // false

console.log(regex2.exec(str2).indices); // undefined
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-regexp.prototype.hasIndices]](https://tc39.es/ecma262/multipage/text-processing.html#sec-get-regexp.prototype.hasIndices)

  -------------------------------------------------------------------------------------------------------------------------------------------


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

`hasIndices`

90

90

88

76

15

90

88

64

15

15.0

90

1.8

16.0.0

 
See also 
--------

 
-   [`RegExp.prototype.lastIndex`](lastindex)
-   [`RegExp.prototype.exec()`](exec)
-   [`RegExp.prototype.dotAll`](dotall)
-   [`RegExp.prototype.global`](global)
-   [`RegExp.prototype.ignoreCase`](ignorecase)
-   [`RegExp.prototype.multiline`](multiline)
-   [`RegExp.prototype.source`](source)
-   [`RegExp.prototype.sticky`](sticky)
-   [`RegExp.prototype.unicode`](unicode)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/hasIndices>

