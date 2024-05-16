handler.has()
=============

 
The `handler.has()` method is a trap for the `[[HasProperty]]` [object
internal method](../../proxy#object_internal_methods), which is used by
operations such as the [`in`](../../../operators/in) operator.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
new Proxy(target, {
  has(target, prop) {
  }
});
```




 
### Parameters

 
The following parameters are passed to `has()` method. `this` is bound
to the handler.

[`target`](#target)

:   The target object.

[`prop`](#prop)

:   The name or [`Symbol`](../../symbol) of the property to check for
    existence.



 
### Return value 

 
The `has()` method must return a boolean value.



 
Description
-----------


 
### Interceptions

 
This trap can intercept these operations:

-   The [`in`](../../../operators/in) operator: `foo in proxy`
-   [`with`](../../../statements/with) check: `with(proxy) { (foo); }`
-   [`Reflect.has()`](../../reflect/has)

Or any other operation that invokes the `[[HasProperty]]` [internal
method](../../proxy#object_internal_methods).



 
### Invariants

 
If the following invariants are violated, the trap throws a
[`TypeError`](../../typeerror) when invoked.

-   A property cannot be reported as non-existent, if it exists as a
    non-configurable own property of the target object.
-   A property cannot be reported as non-existent, if it exists as an
    own property of the target object and the target object is not
    extensible.



 
Examples
--------


 
### Trapping the in operator 

 
The following code traps the [`in`](../../../operators/in) operator.

 
 
[js]


```js
const p = new Proxy(
  {},
  {
    has(target, prop) {
      console.log(`called: ${prop}`);
      return true;
    },
  },
);

console.log("a" in p);
// "called: a"
// true
```


The following code violates an invariant.

 
 
[js]


```js
const obj = { a: 10 };
Object.preventExtensions(obj);

const p = new Proxy(obj, {
  has(target, prop) {
    return false;
  },
});

"a" in p; // TypeError is thrown
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-proxy-object-internal-methods-and-internal-slots-hasproperty-p]](https://tc39.es/ecma262/multipage/ordinary-and-exotic-objects-behaviours.html#sec-proxy-object-internal-methods-and-internal-slots-hasproperty-p)

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`has`

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
-   [`in`](../../../operators/in)
-   [`Reflect.has()`](../../reflect/has)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy/Proxy/has>

