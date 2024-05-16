String.prototype.link()
=======================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


The `link()` method of [`String`](../string) values creates a string
that embeds this string in an
[`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)
element (`<a href="...">str</a>`), to be used as a hypertext link to
another URL.

 
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
link(url)
```




 
### Parameters

 

[`url`](#url)

:   Any string that specifies the `href` attribute of the `<a>` element;
    it should be a valid URL (relative or absolute), with any `&`
    characters escaped as `&amp;`.



 
### Return value 

 
A string beginning with an `<a href="url">` start tag (double quotes in
`url` are replaced with `&quot;`), then the text `str`, and then an
`</a>` end tag.



 
Examples
--------


 
### Using link() 

 
The code below creates an HTML string and then replaces the document\'s
body with it:

 
 
[js]


```js
const contentString = "MDN Web Docs";

document.body.innerHTML = contentString.link("https://developer.mozilla.org/");
```


This will create the following HTML:

 
 
[html]


```html
<a href="https://developer.mozilla.org/">MDN Web Docs</a>
```


Instead of using `link()` and creating HTML text directly, you should
use DOM APIs such as
[`document.createElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement).
For example:

 
 
[js]


```js
const contentString = "MDN Web Docs";
const elem = document.createElement("a");
elem.href = "https://developer.mozilla.org/";
elem.innerText = contentString;
document.body.appendChild(elem);
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.link]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#sec-string.prototype.link)

  -------------------------------------------------------------------------------------------------------------------------------------------------------


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

`link`

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

 
-   [Polyfill of `String.prototype.link` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [HTML wrapper methods](../string#html_wrapper_methods)
-   [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/link>

