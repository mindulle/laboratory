globalThis
==========

 
The `globalThis` global property contains the [global
`this`](../operators/this#global_context) value, which is usually akin
to the [global
object](https://developer.mozilla.org/en-US/docs/Glossary/Global_object).


 
Try it 
------

 



 
Value
-----

 
The global `this` object.

 
Property attributes of `globalThis`




Writable

yes

Enumerable

no

Configurable

yes

 
**Note:** The `globalThis` property is configurable and writable so that
code authors can hide it when executing untrusted code and prevent
exposing the global object.


 
Description
-----------

 
Historically, accessing the global object has required different syntax
in different JavaScript environments. On the web you can use
[`window`](https://developer.mozilla.org/en-US/docs/Web/API/Window/window),
[`self`](https://developer.mozilla.org/en-US/docs/Web/API/Window/self),
or
[`frames`](https://developer.mozilla.org/en-US/docs/Web/API/Window/frames)
- but in [Web
Workers](https://developer.mozilla.org/en-US/docs/Web/API/Worker) only
`self` will work. In Node.js none of these work, and you must instead
use `global`. The `this` keyword could be used inside functions running
in non--strict mode, but `this` will be `undefined` in modules and
inside functions running in strict mode. You can also use
`Function('return this')()`, but environments that disable
[`eval()`](eval), like
[CSP](https://developer.mozilla.org/en-US/docs/Glossary/CSP) in
browsers, prevent use of [`Function`](function) in this way.

The `globalThis` property provides a standard way of accessing the
global `this` value (and hence the global object itself) across
environments. Unlike similar properties such as `window` and `self`,
it\'s guaranteed to work in window and non-window contexts. In this way,
you can access the global object in a consistent manner without having
to know which environment the code is being run in. To help you remember
the name, just remember that in global scope the `this` value is
`globalThis`.

 
**Note:** `globalThis` is generally the same concept as the global
object (i.e. adding properties to `globalThis` makes them global
variables) --- this is the case for browsers and Node --- but hosts are
allowed to provide a different value for `globalThis` that\'s unrelated
to the global object.




 
### HTML and the WindowProxy 

 
In many engines `globalThis` will be a reference to the actual global
object, but in web browsers, due to iframe and cross-window security
considerations, it references a [`Proxy`](proxy) around the actual
global object (which you can\'t directly access). This distinction is
rarely relevant in common usage, but important to be aware of.



 
### Naming

 
Several other popular name choices such as `self` and `global` were
removed from consideration because of their potential to break
compatibility with existing code. See the [language proposal\'s
\"naming\"
document](https://github.com/tc39/proposal-global/blob/master/NAMING.md)
for more details.

`globalThis` is, quite literally, the global `this` value. It\'s the
same value as the `this` value in a non-strict function called without
an object. It\'s also the value of `this` in the global scope of a
script.



 
Examples
--------


 
### Search for the global across environments 

 
Usually, the global object does not need to be explicitly specified ---
its properties are automatically accessible as global variables.

 
 
[js]


```js
console.log(window.Math === Math); // true
```


However, one case where one needs to explicitly access the global object
is when *writing* to it, usually for the purpose of
[polyfills](https://developer.mozilla.org/en-US/docs/Glossary/Polyfill).

Prior to `globalThis`, the only reliable cross-platform way to get the
global object for an environment was `Function('return this')()`.
However, this causes
[CSP](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) violations
in some settings, so authors would use a piecewise definition like this
(slightly adapted from the [original core-js
source](https://github.com/zloirock/core-js/blob/master/packages/core-js/internals/global.js)):

 
 
[js]


```js
function check(it) {
  // Math is known to exist as a global in every environment.
  return it && it.Math === Math && it;
}

const globalObject =
  check(typeof window === "object" && window) ||
  check(typeof self === "object" && self) ||
  check(typeof global === "object" && global) ||
  // This returns undefined when running in strict mode
  (function () {
    return this;
  })() ||
  Function("return this")();
```


After obtaining the global object, we can define new globals on it. For
example, adding an implementation for [`Intl`](intl):

 
 
[js]


```js
if (typeof globalObject.Intl === "undefined") {
  // No Intl in this environment; define our own on the global scope
  Object.defineProperty(globalObject, "Intl", {
    value: {
      // Our Intl implementation
    },
    enumerable: false,
    configurable: true,
    writable: true,
  });
}
```


With `globalThis` available, the additional search for the global across
environments is not necessary anymore:

 
 
[js]


```js
if (typeof globalThis.Intl === "undefined") {
  Object.defineProperty(globalThis, "Intl", {
    value: {
      // Our Intl implementation
    },
    enumerable: false,
    configurable: true,
    writable: true,
  });
}
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-globalthis]](https://tc39.es/ecma262/multipage/global-object.html#sec-globalthis)

  -----------------------------------------------------------------------------------------------


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

`globalThis`

71

79

65

58

12.1

71

65

50

12.2

10.0

71

1.0

12.0.0

 
See also 
--------

 
-   [Polyfill of `globalThis` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-globalthis)
-   [`this`](../operators/this)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/globalThis>

