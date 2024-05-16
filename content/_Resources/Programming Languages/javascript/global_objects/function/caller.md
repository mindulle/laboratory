Function.prototype.caller
=========================

 
 
**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.


 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


 
**Note:** In [strict mode](../../strict_mode), accessing `caller` of a
function throws an error --- the API is removed with no replacement.
This is to prevent code from being able to \"walk the stack\", which
both poses security risks and severely limits the possibility of
optimizations like inlining and tail-call optimization. For more
explanation, you can read [the rationale for the deprecation of
`arguments.callee`](../../functions/arguments/callee#description).


The `caller` accessor property of [`Function`](../function) instances
returns the function that invoked this function. For
[strict](../../strict_mode), arrow, async, and generator functions,
accessing the `caller` property throws a [`TypeError`](../typeerror).


 
Description
-----------

 
If the function `f` was invoked by the top-level code, the value of
`f.caller` is [`null`](../../operators/null); otherwise it\'s the
function that called `f`. If the function that called `f` is a strict
mode function, the value of `f.caller` is also `null`.

Note that the only behavior specified by the ECMAScript specification is
that `Function.prototype` has an initial `caller` accessor that
unconditionally throws a [`TypeError`](../typeerror) for any `get` or
`set` request (known as a \"poison pill accessor\"), and that
implementations are not allowed to change this semantic for any function
except non-strict plain functions, in which case it must not have the
value of a strict mode function. The actual behavior of the `caller`
property, if it\'s anything other than throwing an error, is
implementation-defined. For example, Chrome defines it as an own data
property, while Firefox and Safari extend the initial poison-pill
`Function.prototype.caller` accessor to specially handle `this` values
that are non-strict functions.

 
 
[js]


```js
(function f() {
  if (Object.hasOwn(f, "caller")) {
    console.log(
      "caller is an own property with descriptor",
      Object.getOwnPropertyDescriptor(f, "caller"),
    );
  } else {
    console.log(
      "f doesn't have an own property named caller. Trying to get f.[[Prototype]].caller",
    );
    console.log(
      Object.getOwnPropertyDescriptor(
        Object.getPrototypeOf(f),
        "caller",
      ).get.call(f),
    );
  }
})();

// In Chrome:
// caller is an own property with descriptor {value: null, writable: false, enumerable: false, configurable: false}

// In Firefox:
// f doesn't have an own property named caller. Trying to get f.[[Prototype]].caller
// null
```


This property replaces the obsolete `arguments.caller` property of the
[`arguments`](../../functions/arguments) object.

The special property `__caller__`, which returned the activation object
of the caller thus allowing to reconstruct the stack, was removed for
security reasons.



 
Examples
--------


 
### Checking the value of a function\'s caller property 

 
The following code checks the value a function\'s `caller` property.

 
 
[js]


```js
function myFunc() {
  if (myFunc.caller === null) {
    return "The function was called from the top!";
  } else {
    return `This function's caller was ${myFunc.caller}`;
  }
}
```




 
### Reconstructing the stack and recursion 

 
Note that in case of recursion, you can\'t reconstruct the call stack
using this property. Consider:

 
 
[js]


```js
function f(n) {
  g(n - 1);
}
function g(n) {
  if (n > 0) {
    f(n);
  } else {
    stop();
  }
}
f(2);
```


At the moment `stop()` is called the call stack will be:

```text
f(2) -> g(1) -> f(1) -> g(0) -> stop()
```

The following is true:

 
 
[js]


```js
stop.caller === g && f.caller === g && g.caller === f;
```


so if you tried to get the stack trace in the `stop()` function like
this:

 
 
[js]


```js
let f = stop;
let stack = "Stack trace:";
while (f) {
  stack += `\n${f.name}`;
  f = f.caller;
}
```


the loop would never stop.



 
### Strict mode caller 

 
If the caller is a strict mode function, the value of `caller` is
`null`.

 
 
[js]


```js
function callerFunc() {
  calleeFunc();
}

function strictCallerFunc() {
  "use strict";
  calleeFunc();
}

function calleeFunc() {
  console.log(calleeFunc.caller);
}

(function () {
  callerFunc();
})();
// Logs [Function: callerFunc]

(function () {
  strictCallerFunc();
})();
// Logs null
```




 
Specifications
--------------

 
Not part of any standard.



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

`caller`

1

12

1

9.6

3

18

4

10.1

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [`Function.prototype.name`](name)
-   [`arguments`](../../functions/arguments)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/caller>

