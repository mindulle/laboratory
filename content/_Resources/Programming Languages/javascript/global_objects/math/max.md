Math.max()
==========

 
The `Math.max()` static method returns the largest of the numbers given
as input parameters, or -[`Infinity`](../infinity) if there are no
parameters.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.max()
Math.max(value1)
Math.max(value1, value2)
Math.max(value1, value2, /* …, */ valueN)
```




 
### Parameters

 

[`value1`](#value1), ..., `valueN`

:   Zero or more numbers among which the largest value will be selected
    and returned.



 
### Return value 

 
The largest of the given numbers. Returns [`NaN`](../nan) if any of the
parameters is or is converted into `NaN`. Returns
-[`Infinity`](../infinity) if no parameters are provided.



 
Description
-----------

 
Because `max()` is a static method of `Math`, you always use it as
`Math.max()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).

[`Math.max.length`](../function/length) is 2, which weakly signals that
it\'s designed to handle at least two parameters.



 
Examples
--------


 
### Using Math.max() 

 
 
 
[js]


```js
Math.max(10, 20); // 20
Math.max(-10, -20); // -10
Math.max(-10, 20); // 20
```




 
### Getting the maximum element of an array 

 
[`Array.prototype.reduce()`](../array/reduce) can be used to find the
maximum element in a numeric array, by comparing each value:

 
 
[js]


```js
const arr = [1, 2, 3];
const max = arr.reduce((a, b) => Math.max(a, b), -Infinity);
```


The following function uses
[`Function.prototype.apply()`](../function/apply) to get the maximum of
an array. `getMaxOfArray([1, 2, 3])` is equivalent to
`Math.max(1, 2, 3)`, but you can use `getMaxOfArray()` on
programmatically constructed arrays. This should only be used for arrays
with relatively few elements.

 
 
[js]


```js
function getMaxOfArray(numArray) {
  return Math.max.apply(null, numArray);
}
```


The [spread syntax](../../operators/spread_syntax) is a shorter way of
writing the `apply` solution to get the maximum of an array:

 
 
[js]


```js
const arr = [1, 2, 3];
const max = Math.max(...arr);
```


However, both spread (`...`) and `apply` will either fail or return the
wrong result if the array has too many elements, because they try to
pass the array elements as function parameters. See [Using apply and
built-in
functions](../function/apply#using_apply_and_built-in_functions) for
more details. The `reduce` solution does not have this problem.



Specifications
--------------

 
  -----------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.max]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.max)

  -----------------------------------------------------------------------------------------------


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

`max`

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

 
-   [`Math.min()`](min)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/max>

