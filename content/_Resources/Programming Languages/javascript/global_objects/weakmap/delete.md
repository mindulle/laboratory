WeakMap.prototype.delete()
==========================

 
The `delete()` method of [`WeakMap`](../weakmap) instances removes the
specified element from this `WeakMap`.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
weakMapInstance.delete(key)
```




 
### Parameters

 

[`key`](#key)

:   The key of the element to remove from the `WeakMap` object.



 
### Return value 

 
`true` if an element in the `WeakMap` object has been removed
successfully. `false` if the key is not found in the `WeakMap`. Always
returns `false` if `key` is not an object or a [non-registered
symbol](../symbol#shared_symbols_in_the_global_symbol_registry).



 
Examples
--------


 
### Using the delete() method 

 
 
 
[js]


```js
const wm = new WeakMap();
wm.set(window, "foo");

wm.delete(window); // Returns true. Successfully removed.

wm.has(window); // Returns false. The window object is no longer in the WeakMap.
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-weakmap.prototype.delete]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-weakmap.prototype.delete)

  -------------------------------------------------------------------------------------------------------------------------------


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

`delete`

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



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap/delete>

