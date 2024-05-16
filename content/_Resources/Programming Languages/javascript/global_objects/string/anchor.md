String.prototype.anchor()
=========================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


The `anchor()` method of [`String`](../string) values creates a string
that embeds this string in an
[`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)
element with a name (`<a name="...">str</a>`).

 
**Note:** All [HTML wrapper methods](../string#html_wrapper_methods) are
deprecated and only standardized for compatibility purposes. Use [DOM
APIs](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)
such as
[`document.createElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement)
instead.

The HTML specification no longer allows the
[`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)
element to have a `name` attribute, so this method doesn\'t even create
valid markup.



 
Syntax
------

 
 
 
[js]


```js
anchor(name)
```




 
### Parameters

 

[`name`](#name)

:   A string representing a `name` value to put into the generated
    `<a name="...">` start tag.



 
### Return value 

 
A string beginning with an `<a name="name">` start tag (double quotes in
`name` are replaced with `&quot;`), then the text `str`, and then an
`</a>` end tag.



 
Examples
--------


 
### Using anchor() 

 
The code below creates an HTML string and then replaces the document\'s
body with it:

 
 
[js]


```js
const contentString = "Hello, world";

document.body.innerHTML = contentString.anchor("hello");
```


This will create the following HTML:

 
 
[html]


```html
<a name="hello">Hello, world</a>
```


 
**Warning:** This markup is invalid, because `name` is no longer a valid
attribute of the
[`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)
element.


Instead of using `anchor()` and creating HTML text directly, you should
use DOM APIs such as
[`document.createElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement).
For example:

 
 
[js]


```js
const contentString = "Hello, world";
const elem = document.createElement("a");
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
  sec-string.prototype.anchor]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#sec-string.prototype.anchor)

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

`anchor`

1

12

1Starting with version 17, the quotation mark (\") is replaced by its
HTML reference character (`"`) in strings supplied for the `name`
parameter.

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

 
-   [Polyfill of `String.prototype.anchor` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [HTML wrapper methods](../string#html_wrapper_methods)
-   [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/anchor>

