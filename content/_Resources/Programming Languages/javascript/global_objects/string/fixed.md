String.prototype.fixed()
========================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


The `fixed()` method of [`String`](../string) values creates a string
that embeds this string in a
[`<tt>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tt)
element (`<tt>str</tt>`), which causes this string to be displayed in a
fixed-width font.

 
**Note:** All [HTML wrapper methods](../string#html_wrapper_methods) are
deprecated and only standardized for compatibility purposes. For the
case of `fixed()`, the `<tt>` element itself has been removed from the
HTML specification and shouldn\'t be used anymore. Web developers should
use [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) properties
instead.



 
Syntax
------

 
 
 
[js]


```js
fixed()
```




 
### Parameters

 
None.



 
### Return value 

 
A string beginning with a `<tt>` start tag, then the text `str`, and
then a `</tt>` end tag.



 
Examples
--------


 
### Using fixed() 

 
The code below creates an HTML string and then replaces the document\'s
body with it:

 
 
[js]


```js
const contentString = "Hello, world";

document.body.innerHTML = contentString.fixed();
```


This will create the following HTML:

 
 
[html]


```html
<tt>Hello, world</tt>
```


 
**Warning:** This markup is invalid, because `tt` is no longer a valid
element.


Instead of using `fixed()` and creating HTML text directly, you should
use CSS to manipulate fonts. For example, you can manipulate
[`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)
through the
[`element.style`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)
attribute:

 
 
[js]


```js
document.getElementById("yourElemId").style.fontFamily = "monospace";
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.fixed]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#sec-string.prototype.fixed)

  ---------------------------------------------------------------------------------------------------------------------------------------------------------


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

`fixed`

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

 
-   [Polyfill of `String.prototype.fixed` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [HTML wrapper methods](../string#html_wrapper_methods)
-   [`<tt>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tt)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fixed>

