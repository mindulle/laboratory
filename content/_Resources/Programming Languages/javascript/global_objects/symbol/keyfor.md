Symbol.keyFor()
===============

 
The `Symbol.keyFor()` static method retrieves a shared symbol key from
the global symbol registry for the given symbol.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Symbol.keyFor(sym)
```




 
### Parameters

 

[`sym`](#sym)

:   Symbol, required. The symbol to find a key for.



 
### Return value 

 
A string representing the key for the given symbol if one is found on
the [global
registry](../symbol#shared_symbols_in_the_global_symbol_registry);
otherwise, [`undefined`](../undefined).



 
Examples
--------


 
### Using keyFor() 

 
 
 
[js]


```js
const globalSym = Symbol.for("foo"); // create a new global symbol
Symbol.keyFor(globalSym); // "foo"

const localSym = Symbol();
Symbol.keyFor(localSym); // undefined

// well-known symbols are not symbols registered
// in the global symbol registry
Symbol.keyFor(Symbol.iterator); // undefined
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.keyfor]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.keyfor)

  -----------------------------------------------------------------------------------------------------------


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

`keyFor`

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

 
-   [`Symbol.for()`](for)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/keyFor>

