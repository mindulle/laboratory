Intl.ListFormat.prototype.formatToParts()
=========================================

 
The `formatToParts()` method of [`Intl.ListFormat`](../listformat)
instances returns an [`Array`](../../array) of objects representing the
different components that can be used to format a list of values in a
locale-aware fashion.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
formatToParts(list)
```




 
### Parameters

 

[`list`](#list)

:   An iterable object, such as an [`Array`](../../array), to be
    formatted according to a locale.



 
### Return value 

 
An [`Array`](../../array) of components which contains the formatted
parts from the list.



 
Description
-----------

 
Whereas [`Intl.ListFormat.prototype.format()`](format) returns a string
being the formatted version of the list (according to the given locale
and style options), `formatToParts()` returns an array of the different
components of the formatted string.

Each element of the resulting array has two properties: `type` and
`value`. The `type` property may be either `"element"`, which refers to
a value from the list, or `"literal"` which refers to a linguistic
construct. The `value` property gives the content, as a string, of the
token.

The locale and style options used for formatting are given when
constructing the [`Intl.ListFormat`](../listformat) instance.



 
Examples
--------


 
### Using formatToParts 

 
 
 
[js]


```js
const fruits = ["Apple", "Orange", "Pineapple"];
const myListFormat = new Intl.ListFormat("en-GB", {
  style: "long",
  type: "conjunction",
});

console.table(myListFormat.formatToParts(fruits));
// [
//  { "type": "element", "value": "Apple" },
//  { "type": "literal", "value": ", " },
//  { "type": "element", "value": "Orange" },
//  { "type": "literal", "value": ", and " },
//  { "type": "element", "value": "Pineapple" }
// ]
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Internationalization API Specification\
  [\#
  sec-Intl.ListFormat.prototype.formatToParts]](https://tc39.es/ecma402/#sec-Intl.ListFormat.prototype.formatToParts)

  -----------------------------------------------------------------------------------------------------------------------------


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

`formatToParts`

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
-   [`Intl.ListFormat.prototype.format()`](format)
-   [`Intl.RelativeTimeFormat.prototype.formatToParts()`](../relativetimeformat/formattoparts)
-   [`Intl.NumberFormat.prototype.formatToParts()`](../numberformat/formattoparts)
-   [`Intl.DateTimeFormat.prototype.formatToParts()`](../datetimeformat/formattoparts)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat/formatToParts>

