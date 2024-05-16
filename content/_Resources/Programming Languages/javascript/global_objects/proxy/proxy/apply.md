handler.apply()
===============

 
The `handler.apply()` method is a trap for the `[[Call]]` [object
internal method](../../proxy#object_internal_methods), which is used by
operations such as function calls.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Proxy(target, {
  apply(target, thisArg, argumentsList) {
  }
});
```




 
### Parameters

 
The following parameters are passed to the `apply()` method. `this` is
bound to the handler.

[`target`](#target)

:   The target callable object.

[`thisArg`](#thisarg)

:   The `this` argument for the call.

[`argumentsList`](#argumentslist)

:   The list of arguments for the call.



 
### Return value 

 
The `apply()` method can return any value.



 
Description
-----------


 
### Interceptions

 
This trap can intercept these operations:

-   Function call: `proxy(...args)`
-   [`Function.prototype.apply()`](../../function/apply) and
    [`Function.prototype.call()`](../../function/call)
-   [`Reflect.apply()`](../../reflect/apply)

Or any other operation that invokes the `[[Call]]` [internal
method](../../proxy#object_internal_methods).



 
### Invariants

 
If the following invariants are violated, the trap throws a
[`TypeError`](../../typeerror) when invoked.

-   The `target` must be a callable itself. That is, it must be a
    function object.



 
Examples
--------


 
### Trapping a function call 

 
The following code traps a function call.

 
 
[js]


```js
const p = new Proxy(function () {}, {
  apply(target, thisArg, argumentsList) {
    console.log(`called: ${argumentsList}`);
    return argumentsList[0] + argumentsList[1] + argumentsList[2];
  },
});

console.log(p(1, 2, 3)); // "called: 1,2,3"
// 6
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-proxy-object-internal-methods-and-internal-slots-call-thisargument-argumentslist]](https://tc39.es/ecma262/multipage/ordinary-and-exotic-objects-behaviours.html#sec-proxy-object-internal-methods-and-internal-slots-call-thisargument-argumentslist)

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`apply`

49

12

18

36

10

49

18

36

10

5.0

49

1.0

6.0.0

 
See also 
--------

 
-   [`Proxy`](../../proxy)
-   [`Proxy()` constructor](../proxy)
-   [`Function.prototype.apply()`](../../function/apply)
-   [`Function.prototype.call()`](../../function/call)
-   [`Reflect.apply()`](../../reflect/apply)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/apply>

