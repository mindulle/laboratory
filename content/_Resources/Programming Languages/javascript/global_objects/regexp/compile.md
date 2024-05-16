RegExp.prototype.compile()
==========================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


 
**Note:** The `compile()` method is only specified for compatibility
reasons. Using `compile()` causes the otherwise immutable regex source
and flags to become mutable, which may break user expectations. You can
use the [`RegExp()`](regexp) constructor to construct a new regular
expression object instead.


The `compile()` method of [`RegExp`](../regexp) instances is used to
recompile a regular expression with new source and flags after the
`RegExp` object has already been created.


 
Syntax
------

 
 
 
[js]


```js
compile(pattern, flags)
```




 
### Parameters

 

[`pattern`](#pattern)

:   The text of the regular expression.

[`flags`](#flags)

:   Any combination of [flag values](regexp#flags).



 
### Return value 

 
None ([`undefined`](../undefined)).



 
Examples
--------


 
### Using compile() 

 
The following example shows how to recompile a regular expression with a
new pattern and a new flag.

 
 
[js]


```js
const regexObj = new RegExp("foo", "gi");
regexObj.compile("new foo", "g");
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-regexp.prototype.compile]](https://tc39.es/ecma262/multipage/additional-ecmascript-features-for-web-browsers.html#sec-regexp.prototype.compile)

  -------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`compile`

1

12

1

6

3.1

18

4

10.1

2

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [`RegExp`](../regexp)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/compile>

