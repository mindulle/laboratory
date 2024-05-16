Reflect.apply()
===============

 
The `Reflect.apply()` static method calls a target function with
arguments as specified.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Reflect.apply(target, thisArgument, argumentsList)
```




 
### Parameters

 

[`target`](#target)

:   The target function to call.

[`thisArgument`](#thisargument)

:   The value of `this` provided for the call to `target`.

[`argumentsList`](#argumentslist)

:   An [array-like
    object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#working_with_array-like_objects)
    specifying the arguments with which `target` should be called.



 
### Return value 

 
The result of calling the given `target` function with the specified
`this` value and arguments.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `target` is not a function or `argumentsList` is not an
    object.



 
Description
-----------

 
`Reflect.apply()` provides the reflective semantic of a function call.
That is, `Reflect.apply(target, thisArgument, argumentsList)` is
semantically equivalent to:

 
 
[js]


```js
Math.floor.apply(null, [1.75]);
Reflect.apply(Math.floor, null, [1.75]);
```


The only differences are:

-   `Reflect.apply()` takes the function to call as the `target`
    parameter instead of the `this` context.
-   `Reflect.apply()` throws if `argumentsList` is omitted instead of
    defaulting to calling with no parameters.

`Reflect.apply()` invokes the `[[Call]]` [object internal
method](../proxy#object_internal_methods) of `target`.



 
Examples
--------


 
### Using Reflect.apply() 

 
 
 
[js]


```js
Reflect.apply(Math.floor, undefined, [1.75]);
// 1;

Reflect.apply(String.fromCharCode, undefined, [104, 101, 108, 108, 111]);
// "hello"

Reflect.apply(RegExp.prototype.exec, /ab/, ["confabulation"]).index;
// 4

Reflect.apply("".charAt, "ponies", [3]);
// "i"
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-reflect.apply]](https://tc39.es/ecma262/multipage/reflection.html#sec-reflect.apply)

  --------------------------------------------------------------------------------------------------


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

42

36

10

49

42

36

10

5.0

49

1.0

6.0.0

 
See also 
--------

 
-   [Polyfill of `Reflect.apply` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-reflect)
-   [`Reflect`](../reflect)
-   [`Function.prototype.apply()`](../function/apply)
-   [`handler.apply()`](../proxy/proxy/apply)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/apply>

