Proxy.revocable()
=================

 
The `Proxy.revocable()` static method creates a revocable
[`Proxy`](../proxy) object.


 
Syntax
------

 
 
 
[js]


```js
Proxy.revocable(target, handler)
```




 
### Parameters

 

[`target`](#target)

:   A target object to wrap with `Proxy`. It can be any sort of object,
    including a native array, a function, or even another proxy.

[`handler`](#handler)

:   An object whose properties are functions defining the behavior of
    `proxy` when an operation is performed on it.



 
### Return value 

 
A plain object with the following two properties:

[`proxy`](#proxy)

:   A Proxy object exactly the same as one created with a
    [`new Proxy(target, handler)`](proxy) call.

[`revoke`](#revoke)

:   A function with no parameters to revoke (switch off) the `proxy`.



 
Description
-----------

 
The `Proxy.revocable()` factory function is the same as the
[`Proxy()`](proxy) constructor, except that in addition to creating a
proxy object, it also creates a `revoke` function that can be called to
disable the proxy. The proxy object and the `revoke` function are
wrapped in a plain object.

The `revoke` function does not take any parameters, nor does it rely on
the `this` value. The created `proxy` object is attached to the `revoke`
function as a [private property](privateProperties.md) that
the `revoke` function accesses on itself when called (the existence of
the private property is not observable from the outside, but it has
implications on how garbage collection happens). The `proxy` object is
*not* captured within the
[closure](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
of the `revoke` function (which will make garbage collection of `proxy`
impossible if `revoke` is still alive).

After the `revoke()` function gets called, the proxy becomes unusable:
any trap to a handler throws a [`TypeError`](../typeerror). Once a proxy
is revoked, it remains revoked, and calling `revoke()` again has no
effect --- in fact, the call to `revoke()` detaches the `proxy` object
from the `revoke` function, so the `revoke` function will not be able to
access the proxy again at all. If the proxy is not referenced elsewhere,
it will then be eligible for garbage collection. The `revoke` function
also detaches `target` and `handler` from the `proxy`, so if `target` is
not referenced elsewhere, it will also be eligible for garbage
collection, even when its proxy is still alive, since there\'s no longer
a way to meaningfully interact with the target object.

Letting users interact with an object through a revocable proxy allows
you to [control the
lifetime](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_management)
of the object exposed to the user --- you can make the object
garbage-collectable even when the user is still holding a reference to
its proxy.



 
Examples
--------


 
### Using Proxy.revocable() 

 
 
 
[js]


```js
const revocable = Proxy.revocable(
  {},
  {
    get(target, name) {
      return `[[${name}]]`;
    },
  },
);
const proxy = revocable.proxy;
console.log(proxy.foo); // "[[foo]]"

revocable.revoke();

console.log(proxy.foo); // TypeError is thrown
proxy.foo = 1; // TypeError again
delete proxy.foo; // still TypeError
typeof proxy; // "object", typeof doesn't trigger any trap
```




Specifications
--------------

 
  ------------------------------------------------------------------------------------------------------
  Specification
  ------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-proxy.revocable]](https://tc39.es/ecma262/multipage/reflection.html#sec-proxy.revocable)

  ------------------------------------------------------------------------------------------------------


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

`revocable`

63

12

34

50

10

63

34

46

10

8.0

63

1.0

6.0.0

 
See also 
--------

 
-   [`Proxy`](../proxy)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/revocable>

