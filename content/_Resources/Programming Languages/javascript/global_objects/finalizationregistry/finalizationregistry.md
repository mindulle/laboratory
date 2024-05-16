FinalizationRegistry() constructor
==================================

 
The `FinalizationRegistry()` constructor creates
[`FinalizationRegistry`](../finalizationregistry) objects.


 
Syntax
------

 
 
 
[js]


```js
new FinalizationRegistry(callbackFn)
```


 
**Note:** `FinalizationRegistry()` can only be constructed with
[`new`](../../operators/new). Attempting to call it without `new` throws
a [`TypeError`](../typeerror).




 
### Parameters

 

[`callback`](#callback)

:   A function to be invoked each time a registered target value is
    garbage collected. Its return value is ignored. The function is
    called with the following arguments:

    [`heldValue`](#heldvalue)

    :   The value that was passed to the second parameter of the
        [`register()`](register) method when the `target` object was
        registered.



 
Examples
--------


 
### Creating a new registry 

 
You create the registry passing in the callback:

 
 
[js]


```js
const registry = new FinalizationRegistry((heldValue) => {
  // …
});
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-finalization-registry-constructor]](https://tc39.es/ecma262/multipage/managing-memory.html#sec-finalization-registry-constructor)

  -----------------------------------------------------------------------------------------------------------------------------------------------


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

`FinalizationRegistry`

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

 
-   [`FinalizationRegistry`](../finalizationregistry)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/FinalizationRegistry/FinalizationRegistry>

