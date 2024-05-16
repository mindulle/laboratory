WeakRef() constructor
=====================

 
The `WeakRef()` constructor creates [`WeakRef`](../weakref) objects.


 
Syntax
------

 
 
 
[js]


```js
new WeakRef(target)
```


 
**Note:** `WeakRef()` can only be constructed with
[`new`](../../operators/new). Attempting to call it without `new` throws
a [`TypeError`](../typeerror).




 
### Parameters

 

[`target`](#target)

:   The target value the WeakRef should refer to (also called the
    *referent*). Must be an object or a [non-registered
    symbol](../symbol#shared_symbols_in_the_global_symbol_registry).



 
### Return value 

 
A new `WeakRef` object referring to the given target value.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `target` is not an object or a [non-registered
    symbol](../symbol#shared_symbols_in_the_global_symbol_registry).



 
Examples
--------


 
### Creating a new WeakRef object 

 
See the main [`WeakRef`](../weakref#examples) page for a complete
example.

 
 
[js]


```js
class Counter {
  constructor(element) {
    // Remember a weak reference to a DOM element
    this.ref = new WeakRef(element);
    this.start();
  }
}
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-weak-ref-constructor]](https://tc39.es/ecma262/multipage/managing-memory.html#sec-weak-ref-constructor)

  ---------------------------------------------------------------------------------------------------------------------


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

`WeakRef`

84

84

79

70

14.1

84

79

60

14.5

14.0

84

1.0

14.6.0

 
See also 
--------

 
-   [`WeakRef`](../weakref)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakRef/WeakRef>

