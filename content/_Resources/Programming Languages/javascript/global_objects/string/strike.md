String.prototype.strike()
=========================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


The `strike()` method of [`String`](../string) values creates a string
that embeds this string in a
[`<strike>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strike)
element (`<strike>str</strike>`), which causes this string to be
displayed as struck-out text.

 
**Note:** All [HTML wrapper methods](../string#html_wrapper_methods) are
deprecated and only standardized for compatibility purposes. For the
case of `strike()`, the `<strike>` element itself has been removed from
the HTML specification and shouldn\'t be used anymore. Web developers
should use the
[`<del>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/del)
for deleted content or the
[`<s>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/s) for
content that is no longer accurate or no longer relevant instead.



 
Syntax
------

 
 
 
[js]


```js
strike()
```




 
### Parameters

 
None.



 
### Return value 

 
A string beginning with a `<strike>` start tag, then the text `str`, and
then a `</strike>` end tag.



 
Examples
--------


 
### Using strike() 

 
The code below creates an HTML string and then replaces the document\'s
body with it:

 
 
[js]


```js
const contentString = "Hello, world";

document.body.innerHTML = contentString.strike();
```


This will create the following HTML:

 
 
[html]


```html
<strike>Hello, world</strike>
```


 
**Warning:** This markup is invalid, because `strike` is no longer a
valid element.


Instead of using `strike()` and creating HTML text directly, you should
use DOM APIs such as
[`document.createElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement).
For example:

 
 
[js]


```js
const contentString = "Hello, world";
const elem = document.createElement("s");
elem.innerText = contentString;
document.body.appendChild(elem);
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.strike]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#sec-string.prototype.strike)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------


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

`strike`

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

 
-   [Polyfill of `String.prototype.strike` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [HTML wrapper methods](../string#html_wrapper_methods)
-   [`<strike>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strike)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/strike>

