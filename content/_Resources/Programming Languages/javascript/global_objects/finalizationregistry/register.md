FinalizationRegistry.prototype.register()
=========================================

 
The `register()` method of
[`FinalizationRegistry`](../finalizationregistry) instances registers an
value with this `FinalizationRegistry` so that if the value is
garbage-collected, the registry\'s callback may get called.


 
Syntax
------

 
 
 
[js]


```js
register(target, heldValue)
register(target, heldValue, unregisterToken)
```




 
### Parameters

 

[`target`](#target)

:   The target value to register.

[`heldValue`](#heldvalue)

:   The value to pass to the finalizer for this `target`. This cannot be
    the `target` itself but can be anything else, including functions
    and primitives.

[`unregisterToken`](#unregistertoken) [Optional]

:   A token that may be used with the `unregister` method later to
    unregister the target value. If provided (and not `undefined`), this
    must be an object or a [non-registered
    symbol](../symbol#shared_symbols_in_the_global_symbol_registry). If
    not provided, the target cannot be unregistered.



 
### Return value 

 
None ([`undefined`](../undefined)).



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown in one of the following cases:

    -   `target` is not an object or a [non-registered
        symbol](../symbol#shared_symbols_in_the_global_symbol_registry)
        (object as opposed to primitives; functions are objects as well)
    -   `target` is the same as `heldvalue` (`target === heldValue`)
    -   `unregisterToken` is not an object or a [non-registered
        symbol](../symbol#shared_symbols_in_the_global_symbol_registry)



 
Description
-----------

 
See the [Avoid where
possible](../finalizationregistry#avoid_where_possible) and [Notes on
cleanup callbacks](../finalizationregistry#notes_on_cleanup_callbacks)
sections of the [`FinalizationRegistry`](../finalizationregistry) page
for important caveats.



 
Examples
--------


 
### Using register 

 
The following registers the value referenced by `target`, passing in the
held value `"some value"` and passing the target itself as the
unregistration token:

 
 
[js]


```js
registry.register(target, "some value", target);
```


The following registers the value referenced by `target`, passing in
another object as the held value, and not passing in any unregistration
token (which means `target` can\'t be unregistered):

 
 
[js]


```js
registry.register(target, { useful: "info about target" });
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-finalization-registry.prototype.register]](https://tc39.es/ecma262/multipage/managing-memory.html#sec-finalization-registry.prototype.register)

  -------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`register`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/FinalizationRegistry/register>

