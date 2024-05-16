TypedArray.prototype.toLocaleString()
=====================================

 
The `toLocaleString()` method of [`TypedArray`](../typedarray) instances
returns a string representing the elements of the typed array. The
elements are converted to strings using their `toLocaleString` methods
and these strings are separated by a locale-specific string (such as a
comma \",\"). This method has the same algorithm as
[`Array.prototype.toLocaleString()`](../array/tolocalestring).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toLocaleString()
toLocaleString(locales)
toLocaleString(locales, options)
```




 
### Parameters

 

[`locales`](#locales) [Optional]

:   A string with a BCP 47 language tag, or an array of such strings.
    For the general form and interpretation of the `locales` argument,
    see [the parameter description on the `Intl` main
    page](../intl#locales_argument).

[`options`](#options) [Optional]

:   An object with configuration properties. See
    [`Number.prototype.toLocaleString()`](../number/tolocalestring).



 
### Return value 

 
A string representing the elements of the typed array.



 
Description
-----------

 
See [`Array.prototype.toLocaleString()`](../array/tolocalestring) for
more details. This method is not generic and can only be called on typed
array instances.



 
Examples
--------


 
### Using toLocaleString() 

 
 
 
[js]


```js
const uint = new Uint32Array([2000, 500, 8123, 12, 4212]);

uint.toLocaleString();
// if run in a de-DE locale
// "2.000,500,8.123,12,4.212"

uint.toLocaleString("en-US");
// "2,000,500,8,123,12,4,212"

uint.toLocaleString("ja-JP", { style: "currency", currency: "JPY" });
// "￥2,000,￥500,￥8,123,￥12,￥4,212"
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.tolocalestring]](#)

  -----------------------------------------------------------------------


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

`toLocaleString`

7

12

51

11.6

5.1

18

51

12

5

1.0

≤37

1.0

0.10.0

 
See also 
--------

 
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.toString()`](tostring)
-   [`Array.prototype.toLocaleString()`](../array/tolocalestring)
-   [`Intl`](../intl)
-   [`Intl.ListFormat`](../intl/listformat)
-   [`Number.prototype.toLocaleString()`](../number/tolocalestring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/toLocaleString>

