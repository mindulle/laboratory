String.prototype.startsWith()
=============================

 
The `startsWith()` method of [`String`](../string) values determines
whether this string begins with the characters of a specified string,
returning `true` or `false` as appropriate.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
startsWith(searchString)
startsWith(searchString, position)
```




 
### Parameters

 

[`searchString`](#searchstring)

:   The characters to be searched for at the start of this string.
    Cannot [be a regex](../regexp#special_handling_for_regexes). All
    values that are not regexes are [coerced to
    strings](../string#string_coercion), so omitting it or passing
    `undefined` causes `startsWith()` to search for the string
    `"undefined"`, which is rarely what you want.

[`position`](#position) [Optional]

:   The start position at which `searchString` is expected to be found
    (the index of `searchString`\'s first character). Defaults to `0`.



 
### Return value 

 
`true` if the given characters are found at the beginning of the string,
including when `searchString` is an empty string; otherwise, `false`.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `searchString` [is a
    regex](../regexp#special_handling_for_regexes).



 
Description
-----------

 
This method lets you determine whether or not a string begins with
another string. This method is case-sensitive.



 
Examples
--------


 
### Using startsWith() 

 
 
 
[js]


```js
const str = "To be, or not to be, that is the question.";

console.log(str.startsWith("To be")); // true
console.log(str.startsWith("not to be")); // false
console.log(str.startsWith("not to be", 10)); // true
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.startswith]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.startswith)

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

`startsWith`

41

12

17

28

9

36

17

24

9

3.0

37

1.0

4.0.0

 
See also 
--------

 
-   [Polyfill of `String.prototype.startsWith` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.prototype.endsWith()`](endswith)
-   [`String.prototype.includes()`](includes)
-   [`String.prototype.indexOf()`](indexof)
-   [`String.prototype.lastIndexOf()`](lastindexof)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/startsWith>

