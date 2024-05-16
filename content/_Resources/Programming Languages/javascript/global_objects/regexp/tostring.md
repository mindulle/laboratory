RegExp.prototype.toString()
===========================

 
The `toString()` method of [`RegExp`](../regexp) instances returns a
string representing this regular expression.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toString()
```




 
### Parameters

 
None.



 
### Return value 

 
A string representing the given object.



 
Description
-----------

 
The [`RegExp`](../regexp) object overrides the `toString()` method of
the [`Object`](../object) object; it does not inherit
[`Object.prototype.toString()`](../object/tostring). For
[`RegExp`](../regexp) objects, the `toString()` method returns a string
representation of the regular expression.

In practice, it reads the regex\'s [`source`](source) and
[`flags`](flags) properties and returns a string in the form
`/source/flags`. The `toString()` return value is guaranteed to be a
parsable regex literal, although it may not be the exact same text as
what was originally specified for the regex (for example, the flags may
be reordered).



 
Examples
--------


 
### Using toString() 

 
The following example displays the string value of a
[`RegExp`](../regexp) object:

 
 
[js]


```js
const myExp = new RegExp("a+b+c");
console.log(myExp.toString()); // '/a+b+c/'

const foo = new RegExp("bar", "g");
console.log(foo.toString()); // '/bar/g'
```




 
### Empty regular expressions and escaping 

 
Since `toString()` accesses the [`source`](source) property, an empty
regular expression returns the string `"/(?:)/"`, and line terminators
such as `\n` are escaped. This makes the returned value always a valid
regex literal.

 
 
[js]


```js
new RegExp().toString(); // "/(?:)/"

new RegExp("\n").toString() === "/\\n/"; // true
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-regexp.prototype.tostring]](https://tc39.es/ecma262/multipage/text-processing.html#sec-regexp.prototype.tostring)

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

`toString`

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

`escaping`

73

12

38

60

6

73

38

52

6

11.0

73

1.0

12.0.0

 
See also 
--------

 
-   [`Object.prototype.toString()`](../object/tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/toString>

