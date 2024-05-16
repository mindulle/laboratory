String.prototype.sub()
======================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


The `sub()` method of [`String`](../string) values creates a string that
embeds this string in a
[`<sub>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sub)
element (`<sub>str</sub>`), which causes this string to be displayed as
subscript.

 
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
sub()
```




 
### Parameters

 
None.



 
### Return value 

 
A string beginning with a `<sub>` start tag, then the text `str`, and
then a `</sub>` end tag.



 
Examples
--------


 
### Using sub() 

 
The code below creates an HTML string and then replaces the document\'s
body with it:

 
 
[js]


```js
const contentString = "Hello, world";

document.body.innerHTML = contentString.sub();
```


This will create the following HTML:

 
 
[html]


```html
<sub>Hello, world</sub>
```


Instead of using `sub()` and creating HTML text directly, you should use
DOM APIs such as
[`document.createElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement).
For example:

 
 
[js]


```js
const contentString = "Hello, world";
const elem = document.createElement("sub");
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
  sec-string.prototype.sub]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#sec-string.prototype.sub)

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

`sub`

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

 
-   [Polyfill of `String.prototype.sub` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [HTML wrapper methods](../string#html_wrapper_methods)
-   [`<sub>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sub)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/sub>

