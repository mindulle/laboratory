WeakRef.prototype.deref()
=========================

 
The `deref()` method of [`WeakRef`](../weakref) instances returns this
`WeakRef`\'s target value, or `undefined` if the target value has been
garbage-collected.


 
Syntax
------

 
 
 
[js]


```js
deref()
```




 
### Parameters

 
None.



 
### Return value 

 
The target value of the WeakRef, which is either an object or a
[non-registered
symbol](../symbol#shared_symbols_in_the_global_symbol_registry). Returns
`undefined` if the value has been garbage-collected.



 
Description
-----------

 
See the [Notes on WeakRefs](../weakref#notes_on_weakrefs) section of the
[`WeakRef`](../weakref) page for some important notes.



 
Examples
--------


 
### Using deref() 

 
See the [Examples](../weakref#examples) section of the
[`WeakRef`](../weakref) page for the complete example.

 
 
[js]


```js
const tick = () => {
  // Get the element from the weak reference, if it still exists
  const element = this.ref.deref();
  if (element) {
    element.textContent = ++this.count;
  } else {
    // The element doesn't exist anymore
    console.log("The element is gone.");
    this.stop();
    this.ref = null;
  }
};
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-weak-ref.prototype.deref]](https://tc39.es/ecma262/multipage/managing-memory.html#sec-weak-ref.prototype.deref)

  -----------------------------------------------------------------------------------------------------------------------------


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

`deref`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakRef/deref>

