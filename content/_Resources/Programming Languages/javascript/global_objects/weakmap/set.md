WeakMap.prototype.set()
=======================

 
The `set()` method of [`WeakMap`](../weakmap) instances adds a new
element with a specified key and value to this `WeakMap`.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
set(key, value)
```




 
### Parameters

 

[`key`](#key)

:   Must be either an object or a [non-registered
    symbol](../symbol#shared_symbols_in_the_global_symbol_registry). The
    key of the entry to add to the `WeakMap` object.

[`value`](#value)

:   Any value representing the value of the entry to add to the
    `WeakMap` object.



 
### Return value 

 
The `WeakMap` object.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `key` is not an object or a [non-registered
    symbol](../symbol#shared_symbols_in_the_global_symbol_registry).



 
Examples
--------


 
### Using the set() method 

 
 
 
[js]


```js
const wm = new WeakMap();
const obj = {};

// Add new elements to the WeakMap
wm.set(obj, "foo").set(window, "bar"); // chainable

// Update an element in the WeakMap
wm.set(obj, "baz");

// Using a non-registered symbol as key
const sym = Symbol("foo");
wm.set(sym, "baz");
wm.set(Symbol.iterator, "qux");
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-weakmap.prototype.set]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-weakmap.prototype.set)

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

`set`

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
-   [`WeakMap.prototype.get()`](get)
-   [`WeakMap.prototype.has()`](has)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap/set>

