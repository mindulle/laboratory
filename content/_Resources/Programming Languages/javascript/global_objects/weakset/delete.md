WeakSet.prototype.delete()
==========================

 
The `delete()` method of [`WeakSet`](../weakset) instances removes the
specified element from this `WeakSet`.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
weakSetInstance.delete(value)
```




 
### Parameters

 

[`value`](#value)

:   The value to remove from the `WeakSet` object.



 
### Return value 

 
`true` if an element in the `WeakSet` object has been removed
successfully. `false` if the `value` is not found in the `WeakSet`.
Always returns `false` if `value` is not an object or a [non-registered
symbol](../symbol#shared_symbols_in_the_global_symbol_registry).



 
Examples
--------


 
### Using the delete() method 

 
 
 
[js]


```js
const ws = new WeakSet();
const obj = {};

ws.add(window);

ws.delete(obj); // Returns false. No obj found to be deleted.
ws.delete(window); // Returns true. Successfully removed.

ws.has(window); // Returns false. The window is no longer present in the WeakSet.
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-weakset.prototype.delete]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-weakset.prototype.delete)

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

34

23

9

36

34

24

9

3.0

37

1.0

0.12.0

 
See also 
--------

 
-   [`WeakSet`](../weakset)
-   [`WeakSet.prototype.add()`](add)
-   [`WeakSet.prototype.has()`](has)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet/delete>

