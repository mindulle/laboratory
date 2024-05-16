Intl.ListFormat.prototype.format()
==================================

 
The `format()` method of [`Intl.ListFormat`](../listformat) instances
returns a string with a language-specific representation of the list.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
format()
format(list)
```




 
### Parameters

 

[`list`](#list)

:   An iterable object, such as an Array.



 
### Return value 

 
A language-specific formatted string representing the elements of the
list



 
Description
-----------

 
The `format()` method returns a string that has been formatted based on
parameters provided in the `Intl.ListFormat` object. The `locales` and
`options` parameters customize the behavior of `format()` and let
applications specify the language conventions that should be used to
format the list.



 
Examples
--------


 
### Using format 

 
The following example shows how to create a List formatter using the
English language.

 
 
[js]


```js
const list = ["Motorcycle", "Bus", "Car"];

console.log(
  new Intl.ListFormat("en-GB", { style: "long", type: "conjunction" }).format(
    list,
  ),
);
// Motorcycle, Bus and Car

console.log(
  new Intl.ListFormat("en-GB", { style: "short", type: "disjunction" }).format(
    list,
  ),
);
// Motorcycle, Bus or Car

console.log(
  new Intl.ListFormat("en-GB", { style: "narrow", type: "unit" }).format(list),
);
// Motorcycle Bus Car
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.ListFormat.prototype.format]](https://tc39.es/ecma402/#sec-Intl.ListFormat.prototype.format)

  ---------------------------------------------------------------------------------------------------------------


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

`format`

72

79

78

60

14.1Only available on macOS Big Sur (11) and above.

72

79

51

14.5

11.0

72

1.8

12.0.0Before version 13.0.0, only the locale data for `en-US` is
available by default. See [the `ListFormat()`
constructor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/ListFormat)
for more details.

 
See also 
--------

 
-   [`Intl.ListFormat`](../listformat)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/format>

