WeakSet.prototype.add()
=======================

 
The `add()` method of [`WeakSet`](../weakset) instances appends a new
object to the end of this `WeakSet`.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
add(value)
```




 
### Parameters

 

[`value`](#value)

:   Must be either an object or a [non-registered
    symbol](../symbol#shared_symbols_in_the_global_symbol_registry). The
    value to add to the `WeakSet` collection.



 
### Return value 

 
The `WeakSet` object.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `value` is not an object or a [non-registered
    symbol](../symbol#shared_symbols_in_the_global_symbol_registry).



 
Examples
--------


 
### Using add 

 
 
 
[js]


```js
const ws = new WeakSet();

ws.add(window); // add the window object to the WeakSet

ws.has(window); // true

// WeakSet only takes objects as arguments
ws.add(1);
// results in "TypeError: Invalid value used in weak set" in Chrome
// and "TypeError: 1 is not a non-null object" in Firefox
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-weakset.prototype.add]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-weakset.prototype.add)

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

`add`

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
-   [`WeakSet.prototype.delete()`](delete)
-   [`WeakSet.prototype.has()`](has)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet/add>

