Function.prototype.call()
=========================

 
The `call()` method of [`Function`](../function) instances calls this
function with a given `this` value and arguments provided individually.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
call(thisArg)
call(thisArg, arg1)
call(thisArg, arg1, arg2)
call(thisArg, arg1, arg2, /* …, */ argN)
```




 
### Parameters

 

[`thisArg`](#thisarg)

:   The value to use as `this` when calling `func`. If the function is
    not in [strict mode](../../strict_mode),
    [`null`](../../operators/null) and [`undefined`](../undefined) will
    be replaced with the global object, and primitive values will be
    converted to objects.

[`arg1`](#arg1), ..., `argN` [Optional]

:   Arguments for the function.



 
### Return value 

 
The result of calling the function with the specified `this` value and
arguments.



 
Description
-----------

 
 
**Note:** This function is almost identical to [`apply()`](apply),
except that the function arguments are passed to `call()` individually
as a list, while for `apply()` they are combined in one object,
typically an array --- for example, `func.call(this, "eat", "bananas")`
vs. `func.apply(this, ["eat", "bananas"])`.


Normally, when calling a function, the value of
[`this`](../../operators/this) inside the function is the object that
the function was accessed on. With `call()`, you can assign an arbitrary
value as `this` when calling an existing function, without first
attaching the function to the object as a property. This allows you to
use methods of one object as generic utility functions.

 
**Warning:** Do not use `call()` to chain constructors (for example, to
implement inheritance). This invokes the constructor function as a plain
function, which means [`new.target`](../../operators/new.target) is
`undefined`, and classes throw an error because they can\'t be called
without [`new`](../../operators/new). Use
[`Reflect.construct()`](../reflect/construct) or
[`extends`](../../classes/extends) instead.




 
Examples
--------


 
### Using call() to invoke a function and specifying the this value 

 
In the example below, when we call `greet`, the value of `this` will be
bound to object `obj`, even when `greet` is not a method of `obj`.

 
 
[js]


```js
function greet() {
  console.log(this.animal, "typically sleep between", this.sleepDuration);
}

const obj = {
  animal: "cats",
  sleepDuration: "12 and 16 hours",
};

greet.call(obj); // cats typically sleep between 12 and 16 hours
```




 
### Using call() to invoke a function without specifying the first argument 

 
If the first `thisArg` parameter is omitted, it defaults to `undefined`.
In non-strict mode, the `this` value is then substituted with
[`globalThis`](../globalthis) (which is akin to the global object).

 
 
[js]


```js
globalThis.globProp = "Wisen";

function display() {
  console.log(`globProp value is ${this.globProp}`);
}

display.call(); // Logs "globProp value is Wisen"
```


In strict mode, the value of `this` is not substituted, so it stays as
`undefined`.

 
 
[js]


```js
"use strict";

globalThis.globProp = "Wisen";

function display() {
  console.log(`globProp value is ${this.globProp}`);
}

display.call(); // throws TypeError: Cannot read the property of 'globProp' of undefined
```




 
### Transforming methods to utility functions 

 
`call()` is almost equivalent to a normal function call, except that
`this` is passed as a normal parameter instead of as the value that the
function was accessed on. This is similar to how general-purpose utility
functions work: instead of calling `array.map(callback)`, you use
`map(array, callback)`, which avoids mutating `Array.prototype`, and
allows you to use `map` with array-like objects that are not arrays (for
example, [`arguments`](../../functions/arguments)).

Take [`Array.prototype.slice()`](../array/slice), for example, which you
want to use for converting an array-like object to a real array. You
could create a shortcut like this:

 
 
[js]


```js
const slice = Array.prototype.slice;

// ...

slice.call(arguments);
```


Note that you can\'t save `slice.call` and call it as a plain function,
because the `call()` method also reads its `this` value, which is the
function it should call. In this case, you can use [`bind()`](bind) to
bind the value of `this` for `call()`. In the following piece of code,
`slice()` is a bound version of [`Function.prototype.call()`](call),
with the `this` value bound to
[`Array.prototype.slice()`](../array/slice). This means that additional
`call()` calls can be eliminated:

 
 
[js]


```js
// Same as "slice" in the previous example
const unboundSlice = Array.prototype.slice;
const slice = Function.prototype.call.bind(unboundSlice);

// ...

slice(arguments);
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-function.prototype.call]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-function.prototype.call)

  -------------------------------------------------------------------------------------------------------------------------------


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

`call`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0When calling this method, `thisArg` does not default to the global
object.

 
See also 
--------

 
-   [`Function.prototype.bind()`](bind)
-   [`Function.prototype.apply()`](apply)
-   [`Reflect.apply()`](../reflect/apply)
-   [Spread syntax (`...`)](../../operators/spread_syntax)
-   [Introduction to Object-Oriented
    JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call>

