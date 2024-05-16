WeakMap.prototype.get()
=======================

 
The `get()` method of [`WeakMap`](../weakmap) instances returns a
specified element from this `WeakMap`.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
get(key)
```




 
### Parameters

 

[`key`](#key)

:   The key of the element to return from the `WeakMap` object.



 
### Return value 

 
The element associated with the specified key in the `WeakMap` object.
If the key can\'t be found, [`undefined`](../undefined) is returned.
Always returns `undefined` if `key` is not an object or a
[non-registered
symbol](../symbol#shared_symbols_in_the_global_symbol_registry).



 
Examples
--------


 
### Using the get() method 

 
 
 
[js]


```js
const wm = new WeakMap();
wm.set(window, "foo");

wm.get(window); // Returns "foo".
wm.get("baz"); // Returns undefined.
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-weakmap.prototype.get]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-weakmap.prototype.get)

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

`get`

36

12

6Before Firefox 38, this method threw a `TypeError` when the key
parameter was not an object. However, the ES2015 specification specifies
to return `undefined` instead. Furthermore, `WeakMap.prototype.get`
accepted an optional second argument as a fallback value, which is not
part of the standard. Both non-standard behaviors are removed in version
38 and higher.

23

8

36

6Before Firefox 38, this method threw a `TypeError` when the key
parameter was not an object. However, the ES2015 specification specifies
to return `undefined` instead. Furthermore, `WeakMap.prototype.get`
accepted an optional second argument as a fallback value, which is not
part of the standard. Both non-standard behaviors are removed in version
38 and higher.

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
-   [`WeakMap.prototype.has()`](has)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap/get>

