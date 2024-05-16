String.prototype.fontsize()
===========================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


The `fontsize()` method of [`String`](../string) values creates a string
that embeds this string in a
[`<font>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/font)
element (`<font size="...">str</font>`), which causes this string to be
displayed in the specified font size.

 
**Note:** All [HTML wrapper methods](../string#html_wrapper_methods) are
deprecated and only standardized for compatibility purposes. For the
case of `fontsize()`, the `<font>` element itself has been removed from
the HTML specification and shouldn\'t be used anymore. Web developers
should use [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
properties instead.



 
Syntax
------

 
 
 
[js]


```js
fontsize(size)
```




 
### Parameters

 

[`size`](#size)

:   An integer between 1 and 7, or a string representing a signed
    integer between 1 and 7.



 
### Return value 

 
A string beginning with a `<font size="size">` start tag (double quotes
in `size` are replaced with `&quot;`), then the text `str`, and then a
`</font>` end tag.



 
Description
-----------

 
The `fontsize()` method itself simply joins the string parts together
without any validation or normalization. However, to create valid
[`<font>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/font)
elements, When you specify size as an integer, you set the font size of
`str` to one of the 7 defined sizes. You can specify `size` as a string
such as `"-2"` or `"+3"` to adjust the font size of `str` relative to 3,
the default value.



 
Examples
--------


 
### Using fontsize() 

 
The code below creates an HTML string and then replaces the document\'s
body with it:

 
 
[js]


```js
const contentString = "Hello, world";

document.body.innerHTML = contentString.fontsize(7);
```


This will create the following HTML:

 
 
[html]


```html
<font size="7">Hello, world</font>
```


 
**Warning:** This markup is invalid, because `font` is no longer a valid
element.


Instead of using `fontsize()` and creating HTML text directly, you
should use CSS to manipulate fonts. For example, you can manipulate
[`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size)
through the
[`element.style`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)
attribute:

 
 
[js]


```js
document.getElementById("yourElemId").style.fontSize = "7pt";
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.fontsize]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#sec-string.prototype.fontsize)

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`fontsize`

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

 
-   [Polyfill of `String.prototype.fontsize` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [HTML wrapper methods](../string#html_wrapper_methods)
-   [`<font>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/font)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fontsize>

