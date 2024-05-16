String.prototype.includes()
===========================

 
The `includes()` method of [`String`](../string) values performs a
case-sensitive search to determine whether a given string may be found
within this string, returning `true` or `false` as appropriate.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
includes(searchString)
includes(searchString, position)
```




 
### Parameters

 

[`searchString`](#searchstring)

:   A string to be searched for within `str`. Cannot [be a
    regex](../regexp#special_handling_for_regexes). All values that are
    not regexes are [coerced to strings](../string#string_coercion), so
    omitting it or passing `undefined` causes `includes()` to search for
    the string `"undefined"`, which is rarely what you want.

[`position`](#position) [Optional]

:   The position within the string at which to begin searching for
    `searchString`. (Defaults to `0`.)



 
### Return value 

 
`true` if the search string is found anywhere within the given string,
including when `searchString` is an empty string; otherwise, `false`.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `searchString` [is a
    regex](../regexp#special_handling_for_regexes).



 
Description
-----------

 
This method lets you determine whether or not a string includes another
string.



 
### Case-sensitivity

 
The `includes()` method is case sensitive. For example, the following
expression returns `false`:

 
 
[js]


```js
"Blue Whale".includes("blue"); // returns false
```


You can work around this constraint by transforming both the original
string and the search string to all lowercase:

 
 
[js]


```js
"Blue Whale".toLowerCase().includes("blue"); // returns true
```




 
Examples
--------


 
### Using includes() 

 
 
 
[js]


```js
const str = "To be, or not to be, that is the question.";

console.log(str.includes("To be")); // true
console.log(str.includes("question")); // true
console.log(str.includes("nonexistent")); // false
console.log(str.includes("To be", 1)); // false
console.log(str.includes("TO BE")); // false
console.log(str.includes("")); // true
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.includes]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.includes)

  -------------------------------------------------------------------------------------------------------------------------------


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

`includes`

41

12

4018--48

28

9

41

4018--48

28

9

4.0

41

1.0

4.0.0

 
See also 
--------

 
-   [Polyfill of `String.prototype.includes` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`Array.prototype.includes()`](../array/includes)
-   [`TypedArray.prototype.includes()`](../typedarray/includes)
-   [`String.prototype.indexOf()`](indexof)
-   [`String.prototype.lastIndexOf()`](lastindexof)
-   [`String.prototype.startsWith()`](startswith)
-   [`String.prototype.endsWith()`](endswith)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/includes>

