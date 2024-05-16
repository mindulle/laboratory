arguments.length
================


The `arguments.length` data property contains the number of arguments
passed to the function.



Value
-----


A non-negative integer.


Property attributes of `arguments.length`




Writable

yes

Enumerable

no

Configurable

yes


Description
-----------


The `arguments.length` property provides the number of arguments
actually passed to a function. This can be more or less than the defined
parameter\'s count (see
[`Function.prototype.length`](../../global_objects/function/length)).
For example, for the function below:



[js]


```js
function func1(a, b, c) {
  console.log(arguments.length);
}
```


`func1.length` returns `3`, because `func1` declares three formal
parameters. However, `func1(1, 2, 3, 4, 5)` logs `5`, because `func1`
was called with five arguments. Similarly, `func1(1)` logs `1`, because
`func1` was called with one argument.




Examples
--------



### Using arguments.length 


In this example, we define a function that can add two or more numbers
together.



[js]


```js
function adder(base /*, num1, …, numN */) {
  base = Number(base);
  for (let i = 1; i < arguments.length; i++) {
    base += Number(arguments[i]);
  }
  return base;
}
```




Specifications
--------------


  ----------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-arguments-exotic-objects]](https://tc39.es/ecma262/multipage/ordinary-and-exotic-objects-behaviours.html#sec-arguments-exotic-objects)

  ----------------------------------------------------------------------------------------------------------------------------------------------------


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

4

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


-   [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
    guide
-   [Functions](../../functions)
-   [`arguments`](../arguments)
-   [`Function`: `length`](../../global_objects/function/length)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments/length>

