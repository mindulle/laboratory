String.prototype.fontcolor()
============================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


The `fontcolor()` method of [`String`](../string) values creates a
string that embeds this string in a
[`<font>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/font)
element (`<font color="...">str</font>`), which causes this string to be
displayed in the specified font color.

 
**Note:** All [HTML wrapper methods](../string#html_wrapper_methods) are
deprecated and only standardized for compatibility purposes. For the
case of `fontcolor()`, the `<font>` element itself has been removed from
the HTML specification and shouldn\'t be used anymore. Web developers
should use [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
properties instead.



 
Syntax
------

 
 
 
[js]


```js
fontcolor(color)
```




 
### Parameters

 

[`color`](#color)

:   A string expressing the color as a hexadecimal RGB triplet or as a
    string literal. String literals for color names are listed in the
    [CSS color
    reference](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value).



 
### Return value 

 
A string beginning with a `<font color="color">` start tag (double
quotes in `color` are replaced with `&quot;`), then the text `str`, and
then a `</font>` end tag.



 
Description
-----------

 
The `fontcolor()` method itself simply joins the string parts together
without any validation or normalization. However, to create valid
[`<font>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/font)
elements, if you express color as a hexadecimal RGB triplet, you must
use the format `rrggbb`. For example, the hexadecimal RGB values for
salmon are red=FA, green=80, and blue=72, so the RGB triplet for salmon
is `"FA8072"`.



 
Examples
--------


 
### Using fontcolor() 

 
The code below creates an HTML string and then replaces the document\'s
body with it:

 
 
[js]


```js
const contentString = "Hello, world";

document.body.innerHTML = contentString.fontcolor("red");
```


This will create the following HTML:

 
 
[html]


```html
<font color="red">Hello, world</font>
```


 
**Warning:** This markup is invalid, because `font` is no longer a valid
element.


Instead of using `fontcolor()` and creating HTML text directly, you
should use CSS to manipulate fonts. For example, you can manipulate
[`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color)
through the
[`element.style`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)
attribute:

 
 
[js]


```js
document.getElementById("yourElemId").style.color = "red";
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.fontcolor]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#sec-string.prototype.fontcolor)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`fontcolor`

1

12

1

3

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

 
-   [Polyfill of `String.prototype.fontcolor` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [HTML wrapper methods](../string#html_wrapper_methods)
-   [`<font>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/font)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fontcolor>

