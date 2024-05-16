FinalizationRegistry.prototype.unregister()
===========================================

 
The `unregister()` method of
[`FinalizationRegistry`](../finalizationregistry) instances unregisters
a target value from this `FinalizationRegistry`.


 
Syntax
------

 
 
 
[js]


```js
unregister(unregisterToken)
```




 
### Parameters

 

[`unregisterToken`](#unregistertoken)

:   The token used with the [`register()`](register) method when
    registering the target value. Multiple cells registered with the
    same `unregisterToken` will be unregistered together.



 
### Return value 

 
A boolean value that is `true` if at least one cell was unregistered and
`false` if no cell was unregistered.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `unregisterToken` is not an object or a [non-registered
    symbol](../symbol#shared_symbols_in_the_global_symbol_registry).



 
Description
-----------

 
When a target value has been reclaimed, it is no longer registered in
the registry. There is no need to call `unregister` in your cleanup
callback. Only call `unregister` if you haven\'t received a cleanup
callback and no longer need to receive one.



 
Examples
--------


 
### Using unregister 

 
This example shows registering a target object using that same object as
the unregister token, then later unregistering it via `unregister`:

 
 
[js]


```js
class Thingy {
  static #cleanup = (label) => {
    //               ^^^^^−−−−− held value
    console.error(
      `The "release" method was never called for the object with the label "${label}"`,
    );
  };
  #registry = new FinalizationRegistry(Thingy.#cleanup);

  /**
   * Constructs a `Thingy` instance.
   * Be sure to call `release` when you're done with it.
   *
   * @param label A label for the `Thingy`.
   */
  constructor(label) {
    //                            vvvvv−−−−− held value
    this.#registry.register(this, label, this);
    //          target −−−−−^^^^         ^^^^−−−−− unregister token
  }

  /**
   * Releases resources held by this `Thingy` instance.
   */
  release() {
    this.#registry.unregister(this);
    //                        ^^^^−−−−− unregister token
  }
}
```


This example shows registering a target object using a different object
as its unregister token:

 
 
[js]


```js
class Thingy {
  static #cleanup = (file) => {
    //               ^^^^−−−−− held value
    console.error(
      `The "release" method was never called for the "Thingy" for the file "${file.name}"`,
    );
  };
  #registry = new FinalizationRegistry(Thingy.#cleanup);
  #file;

  /**
   * Constructs a `Thingy` instance for the given file.
   * Be sure to call `release` when you're done with it.
   *
   * @param filename The name of the file.
   */
  constructor(filename) {
    this.#file = File.open(filename);
    //                            vvvvv−−−−− held value
    this.#registry.register(this, label, this.#file);
    //          target −−−−−^^^^         ^^^^^^^^^^−−−−− unregister token
  }

  /**
   * Releases resources held by this `Thingy` instance.
   */
  release() {
    if (this.#file) {
      this.#registry.unregister(this.#file);
      //                        ^^^^^^^^^^−−−−− unregister token
      File.close(this.#file);
      this.#file = null;
    }
  }
}
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-finalization-registry.prototype.unregister]](https://tc39.es/ecma262/multipage/managing-memory.html#sec-finalization-registry.prototype.unregister)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`unregister`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/FinalizationRegistry/unregister>

