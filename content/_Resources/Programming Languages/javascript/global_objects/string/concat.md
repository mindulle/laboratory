String.prototype.concat()
=========================

 
The `concat()` method of [`String`](../string) values concatenates the
string arguments to this string and returns a new string.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
concat()
concat(str1)
concat(str1, str2)
concat(str1, str2, /* …, */ strN)
```




 
### Parameters

 

[`str1`](#str1), ..., `strN`

:   One or more strings to concatenate to `str`.



 
### Return value 

 
A new string containing the combined text of the strings provided.



 
Description
-----------

 
The `concat()` function concatenates the string arguments to the calling
string and returns a new string. Changes to the original string or the
returned string don\'t affect the other.

If the arguments are not of the type string, they are converted to
string values before concatenating.

The `concat()` method is very similar to the [addition/string
concatenation operators](../../operators/addition) (`+`, `+=`), except
that `concat()` [coerces its arguments directly to
strings](../string#string_coercion), while addition coerces its operands
to primitives first. For more information, see the reference page for
the [`+` operator](../../operators/addition).



 
Examples
--------


 
### Using concat() 

 
The following example combines strings into a new string.

 
 
[js]


```js
const hello = "Hello, ";
console.log(hello.concat("Kevin", ". Have a nice day."));
// Hello, Kevin. Have a nice day.

const greetList = ["Hello", " ", "Venkat", "!"];
"".concat(...greetList); // "Hello Venkat!"

"".concat({}); // "[object Object]"
"".concat([]); // ""
"".concat(null); // "null"
"".concat(true); // "true"
"".concat(4, 5); // "45"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.concat]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.concat)

  ---------------------------------------------------------------------------------------------------------------------------


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

`concat`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [`Array.prototype.concat()`](../array/concat)
-   [Addition (`+`)](../../operators/addition)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/concat>

