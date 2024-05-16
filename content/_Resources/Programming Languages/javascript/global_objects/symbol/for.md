Symbol.for()
============

 
The `Symbol.for()` static method searches for existing symbols in a
runtime-wide symbol registry with the given key and returns it if found.
Otherwise a new symbol gets created in the global symbol registry with
this key.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Symbol.for(key)
```




 
### Parameters

 

[`key`](#key)

:   String, required. The key for the symbol (and also used for the
    description of the symbol).



 
### Return value 

 
An existing symbol with the given key if found; otherwise, a new symbol
is created and returned.



 
Description
-----------

 
In contrast to `Symbol()`, the `Symbol.for()` function creates a symbol
available in a [global symbol
registry](../symbol#shared_symbols_in_the_global_symbol_registry) list.
`Symbol.for()` does also not necessarily create a new symbol on every
call, but checks first if a symbol with the given `key` is already
present in the registry. In that case, that symbol is returned. If no
symbol with the given key is found, `Symbol.for()` will create a new
global symbol.



 
Examples
--------


 
### Using Symbol.for() 

 
 
 
[js]


```js
Symbol.for("foo"); // create a new global symbol
Symbol.for("foo"); // retrieve the already created symbol

// Same global symbol, but not locally
Symbol.for("bar") === Symbol.for("bar"); // true
Symbol("bar") === Symbol("bar"); // false

// The key is also used as the description
const sym = Symbol.for("mario");
sym.toString(); // "Symbol(mario)"
```


To avoid name clashes with your global symbol keys and other (library
code) global symbols, it might be a good idea to prefix your symbols:

 
 
[js]


```js
Symbol.for("mdn.foo");
Symbol.for("mdn.bar");
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.for]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.for)

  -----------------------------------------------------------------------------------------------------


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

`for`

40

12

36

27

9

40

36

27

9

4.0

40

1.0

0.12.0

 
See also 
--------

 
-   [`Symbol.keyFor()`](keyfor)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/for>

