Function: length
================

 
The `length` data property of a [`Function`](../function) instance
indicates the number of parameters expected by the function.


 
Try it 
------

 



 
Value
-----

 
A number.

 
Property attributes of `Function: length`




Writable

no

Enumerable

no

Configurable

yes

 
Description
-----------

 
A [`Function`](../function) object\'s `length` property indicates how
many arguments the function expects, i.e. the number of formal
parameters. This number excludes the [rest
parameter](../../functions/rest_parameters) and only includes parameters
before the first one with a default value. By contrast,
[`arguments.length`](../../functions/arguments/length) is local to a
function and provides the number of arguments actually passed to the
function.

The [`Function`](../function) constructor is itself a `Function` object.
Its `length` data property has a value of `1`.

Due to historical reasons, `Function.prototype` is a callable itself.
The `length` property of `Function.prototype` has a value of `0`.



 
Examples
--------


 
### Using function length 

 
 
 
[js]


```js
console.log(Function.length); // 1

console.log((() => {}).length); // 0
console.log(((a) => {}).length); // 1
console.log(((a, b) => {}).length); // 2 etc.

console.log(((...args) => {}).length);
// 0, rest parameter is not counted

console.log(((a, b = 1, c) => {}).length);
// 1, only parameters before the first one with
// a default value are counted
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-function-instances-length]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-function-instances-length)

  -----------------------------------------------------------------------------------------------------------------------------------


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

`length`

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

`configurable_true`

43

12

37

30

10

43

37

30

10

4.0

43

1.0

4.0.0

 
See also 
--------

 
-   [`Function`](../function)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/length>

