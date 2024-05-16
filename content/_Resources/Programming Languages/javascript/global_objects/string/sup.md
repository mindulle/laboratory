String.prototype.sup()
======================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


The `sup()` method of [`String`](../string) values creates a string that
embeds this string in a
[`<sup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sup)
element (`<sup>str</sup>`), which causes this string to be displayed as
superscript.

 
**Note:** All [HTML wrapper methods](../string#html_wrapper_methods) are
deprecated and only standardized for compatibility purposes. Use [DOM
APIs](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)
such as
[`document.createElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement)
instead.



 
Syntax
------

 
 
 
[js]


```js
sup()
```




 
### Parameters

 
None.



 
### Return value 

 
A string beginning with a `<sup>` start tag, then the text `str`, and
then a `</sup>` end tag.



 
Examples
--------


 
### Using sup() 

 
The code below creates an HTML string and then replaces the document\'s
body with it:

 
 
[js]


```js
const contentString = "Hello, world";

document.body.innerHTML = contentString.sup();
```


This will create the following HTML:

 
 
[html]


```html
<sup>Hello, world</sup>
```


Instead of using `sup()` and creating HTML text directly, you should use
DOM APIs such as
[`document.createElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement).
For example:

 
 
[js]


```js
const contentString = "Hello, world";
const elem = document.createElement("sup");
elem.innerText = contentString;
document.body.appendChild(elem);
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.sup]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#sec-string.prototype.sup)

  -----------------------------------------------------------------------------------------------------------------------------------------------------


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

`sup`

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

 
-   [Polyfill of `String.prototype.sup` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [HTML wrapper methods](../string#html_wrapper_methods)
-   [`<sup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sup)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/sup>

