WeakSet.prototype.has()
=======================

 
The `has()` method of [`WeakSet`](../weakset) instances returns a
boolean indicating whether an object exists in this `WeakSet` or not.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
has(value)
```




 
### Parameters

 

[`value`](#value)

:   The value to test for presence in the `WeakSet`.



 
### Return value 

 
Returns `true` if an element with the specified value exists in the
`WeakSet` object; otherwise `false`. Always returns `false` if `value`
is not an object or a [non-registered
symbol](../symbol#shared_symbols_in_the_global_symbol_registry).



 
Examples
--------


 
### Using the `has()` method 

 
 
 
[js]


```js
const ws = new WeakSet();
const obj = {};
ws.add(window);

ws.has(window); // returns true
ws.has(obj); // returns false

// Storing a non-registered symbol
const sym = Symbol("foo");
ws.add(sym);
ws.add(Symbol.iterator);
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-weakset.prototype.has]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-weakset.prototype.has)

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
-   [`WeakSet.prototype.delete()`](delete)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet/has>

