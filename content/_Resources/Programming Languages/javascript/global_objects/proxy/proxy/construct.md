handler.construct()
===================

 
The `handler.construct()` method is a trap for the `[[Construct]]`
[object internal method](../../proxy#object_internal_methods), which is
used by operations such as the [`new`](../../../operators/new) operator.
In order for the new operation to be valid on the resulting Proxy
object, the target used to initialize the proxy must itself be a valid
constructor.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Proxy(target, {
  construct(target, argumentsList, newTarget) {
  }
});
```




 
### Parameters

 
The following parameters are passed to the `construct()` method. `this`
is bound to the handler.

[`target`](#target)

:   The target object.

[`argumentsList`](#argumentslist)

:   The list of arguments for the constructor.

[`newTarget`](#newtarget)

:   The constructor that was originally called.



 
### Return value 

 
The `construct` method must return an object.



 
Description
-----------


 
### Interceptions

 
This trap can intercept these operations:

-   The [`new`](../../../operators/new) operator:
    `new myFunction(...args)`
-   [`Reflect.construct()`](../../reflect/construct)

Or any other operation that invokes the `[[Construct]]` [internal
method](../../proxy#object_internal_methods).



 
### Invariants

 
If the following invariants are violated, the trap throws a
[`TypeError`](../../typeerror) when invoked.

-   The result must be an `Object`.



 
Examples
--------


 
### Trapping the new operator 

 
The following code traps the [`new`](../../../operators/new) operator.

 
 
[js]


```js
const p = new Proxy(function () {}, {
  construct(target, argumentsList, newTarget) {
    console.log(`called: ${argumentsList}`);
    return { value: argumentsList[0] * 10 };
  },
});

console.log(new p(1).value); // "called: 1"
// 10
```


The following code violates the invariant.

 
 
[js]


```js
const p = new Proxy(function () {}, {
  construct(target, argumentsList, newTarget) {
    return 1;
  },
});

new p(); // TypeError is thrown
```


The following code improperly initializes the proxy. The `target` in
Proxy initialization must itself be a valid constructor for the
[`new`](../../../operators/new) operator.

 
 
[js]


```js
const p = new Proxy(
  {},
  {
    construct(target, argumentsList, newTarget) {
      return {};
    },
  },
);

new p(); // TypeError is thrown, "p" is not a constructor
```




Specifications
--------------

 
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-proxy-object-internal-methods-and-internal-slots-construct-argumentslist-newtarget]](https://tc39.es/ecma262/multipage/ordinary-and-exotic-objects-behaviours.html#sec-proxy-object-internal-methods-and-internal-slots-construct-argumentslist-newtarget)

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`construct`

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
-   [`new`](../../../operators/new)
-   [`Reflect.construct()`](../../reflect/construct)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/construct>

