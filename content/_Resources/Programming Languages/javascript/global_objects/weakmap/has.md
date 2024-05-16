WeakMap.prototype.has()
=======================

 
The `has()` method of [`WeakMap`](../weakmap) instances returns a
boolean indicating whether an element with the specified key exists in
this `WeakMap` or not.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
has(key)
```




 
### Parameters

 

[`key`](#key)

:   The key of the element to test for presence in the `WeakMap` object.



 
### Return value 

 
Returns `true` if an element with the specified key exists in the
`WeakMap` object; otherwise `false`. Always returns `false` if `key` is
not an object or a [non-registered
symbol](../symbol#shared_symbols_in_the_global_symbol_registry).



 
Examples
--------


 
### Using the has method 

 
 
 
[js]


```js
const wm = new WeakMap();
wm.set(window, "foo");

wm.has(window); // returns true
wm.has("baz"); // returns false
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-weakmap.prototype.has]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-weakmap.prototype.has)

  -------------------------------------------------------------------------------------------------------------------------


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

`has`

36

12

6Before Firefox 38, this method threw a `TypeError` when the key
parameter was not an object. This has been fixed in version 38 and later
to return `false` as per the ES2015 standard.

23

8

36

6Before Firefox 38, this method threw a `TypeError` when the key
parameter was not an object. This has been fixed in version 38 and later
to return `false` as per the ES2015 standard.

24

8

3.0

37

1.0

0.12.0

 
See also 
--------

 
-   [`WeakMap`](../weakmap)
-   [`WeakMap.prototype.set()`](set)
-   [`WeakMap.prototype.get()`](get)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap/has>

