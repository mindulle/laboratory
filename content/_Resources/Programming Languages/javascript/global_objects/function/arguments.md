Function.prototype.arguments
============================

 
 
**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.


 
**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.


 
**Note:** The `arguments` property of [`Function`](../function) objects
is deprecated. The recommended way to access the `arguments` object is
to refer to the variable [`arguments`](../../functions/arguments)
available within functions.


The `arguments` accessor property of [`Function`](../function) instances
returns the arguments passed to this function. For
[strict](../../strict_mode), arrow, async, and generator functions,
accessing the `arguments` property throws a [`TypeError`](../typeerror).


 
Description
-----------

 
The value of `arguments` is an array-like object corresponding to the
arguments passed to a function.

In the case of recursion, i.e. if function `f` appears several times on
the call stack, the value of `f.arguments` represents the arguments
corresponding to the most recent invocation of the function.

The value of the `arguments` property is normally
[`null`](../../operators/null) if there is no outstanding invocation of
the function in progress (that is, the function has been called but has
not yet returned).

Note that the only behavior specified by the ECMAScript specification is
that `Function.prototype` has an initial `arguments` accessor that
unconditionally throws a [`TypeError`](../typeerror) for any `get` or
`set` request (known as a \"poison pill accessor\"), and that
implementations are not allowed to change this semantic for any function
except non-strict plain functions. The actual behavior of the
`arguments` property, if it\'s anything other than throwing an error, is
implementation-defined. For example, Chrome defines it as an own data
property, while Firefox and Safari extend the initial poison-pill
`Function.prototype.arguments` accessor to specially handle `this`
values that are non-strict functions.

 
 
[js]


```js
(function f() {
  if (Object.hasOwn(f, "arguments")) {
    console.log(
      "arguments is an own property with descriptor",
      Object.getOwnPropertyDescriptor(f, "arguments"),
    );
  } else {
    console.log(
      "f doesn't have an own property named arguments. Trying to get f.[[Prototype]].arguments",
    );
    console.log(
      Object.getOwnPropertyDescriptor(
        Object.getPrototypeOf(f),
        "arguments",
      ).get.call(f),
    );
  }
})();

// In Chrome:
// arguments is an own property with descriptor {value: Arguments(0), writable: false, enumerable: false, configurable: false}

// In Firefox:
// f doesn't have an own property named arguments. Trying to get f.[[Prototype]].arguments
// Arguments { … }
```




 
Examples
--------


 
### Using the arguments property 

 
 
 
[js]


```js
function f(n) {
  g(n - 1);
}

function g(n) {
  console.log(`before: ${g.arguments[0]}`);
  if (n > 0) {
    f(n);
  }
  console.log(`after: ${g.arguments[0]}`);
}

f(2);

console.log(`returned: ${g.arguments}`);

// Logs:
// before: 1
// before: 0
// after: 0
// after: 1
// returned: null
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

`arguments`

1

12

1

3

1

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

 
-   [`arguments`](../../functions/arguments)
-   [Functions](../../functions)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/arguments>

