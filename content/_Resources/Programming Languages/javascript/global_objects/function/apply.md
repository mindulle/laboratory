Function.prototype.apply()
==========================

 
The `apply()` method of [`Function`](../function) instances calls this
function with a given `this` value, and `arguments` provided as an array
(or an [array-like
object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#working_with_array-like_objects)).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
apply(thisArg)
apply(thisArg, argsArray)
```




 
### Parameters

 

[`thisArg`](#thisarg)

:   The value of `this` provided for the call to `func`. If the function
    is not in [strict mode](../../strict_mode),
    [`null`](../../operators/null) and [`undefined`](../undefined) will
    be replaced with the global object, and primitive values will be
    converted to objects.

[`argsArray`](#argsarray) [Optional]

:   An array-like object, specifying the arguments with which `func`
    should be called, or [`null`](../../operators/null) or
    [`undefined`](../undefined) if no arguments should be provided to
    the function.



 
### Return value 

 
The result of calling the function with the specified `this` value and
arguments.



 
Description
-----------

 
 
**Note:** This function is almost identical to [`call()`](call), except
that the function arguments are passed to `call()` individually as a
list, while for `apply()` they are combined in one object, typically an
array --- for example, `func.call(this, "eat", "bananas")` vs.
`func.apply(this, ["eat", "bananas"])`.


Normally, when calling a function, the value of
[`this`](../../operators/this) inside the function is the object that
the function was accessed on. With `apply()`, you can assign an
arbitrary value as `this` when calling an existing function, without
first attaching the function to the object as a property. This allows
you to use methods of one object as generic utility functions.

You can also use any kind of object which is array-like as the second
parameter. In practice, this means that it needs to have a `length`
property, and integer (\"index\") properties in the range
`(0..length - 1)`. For example, you could use a
[`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList),
or a custom object like `{ 'length': 2, '0': 'eat', '1': 'bananas' }`.
You can also use [`arguments`](../../functions/arguments), for example:

 
 
[js]


```js
function wrapper() {
  return anotherFn.apply(null, arguments);
}
```


With the [rest parameters](../../functions/rest_parameters) and
parameter [spread syntax](../../operators/spread_syntax), this can be
rewritten as:

 
 
[js]


```js
function wrapper(...args) {
  return anotherFn(...args);
}
```


In general, `fn.apply(null, args)` is equivalent to `fn(...args)` with
the parameter spread syntax, except `args` is expected to be an
array-like object in the former case with `apply()`, and an
[iterable](../../iteration_protocols#the_iterable_protocol) object in
the latter case with spread syntax.

 
**Warning:** Do not use `apply()` to chain constructors (for example, to
implement inheritance). This invokes the constructor function as a plain
function, which means [`new.target`](../../operators/new.target) is
`undefined`, and classes throw an error because they can\'t be called
without [`new`](../../operators/new). Use
[`Reflect.construct()`](../reflect/construct) or
[`extends`](../../classes/extends) instead.




 
Examples
--------


 
### Using apply() to append an array to another 

 
You can use [`Array.prototype.push()`](../array/push) to append an
element to an array. Because `push()` accepts a variable number of
arguments, you can also push multiple elements at once. But if you pass
an array to `push()`, it will actually add that array as a single
element, instead of adding the elements individually, ending up with an
array inside an array. On the other hand,
[`Array.prototype.concat()`](../array/concat) does have the desired
behavior in this case, but it does not append to the *existing* array
--- it creates and returns a new array.

In this case, you can use `apply` to implicitly \"spread\" an array as a
series of arguments.

 
 
[js]


```js
const array = ["a", "b"];
const elements = [0, 1, 2];
array.push.apply(array, elements);
console.info(array); // ["a", "b", 0, 1, 2]
```


The same effect can be achieved with the spread syntax.

 
 
[js]


```js
const array = ["a", "b"];
const elements = [0, 1, 2];
array.push(...elements);
console.info(array); // ["a", "b", 0, 1, 2]
```




 
### Using apply() and built-in functions 

 
Clever usage of `apply()` allows you to use built-in functions for some
tasks that would probably otherwise require manually looping over a
collection (or using the spread syntax).

For example, we can use [`Math.max()`](../math/max) and
[`Math.min()`](../math/min) to find out the maximum and minimum value in
an array.

 
 
[js]


```js
// min/max number in an array
const numbers = [5, 6, 2, 3, 7];

// using Math.min/Math.max apply
let max = Math.max.apply(null, numbers);
// This about equal to Math.max(numbers[0], …)
// or Math.max(5, 6, …)

let min = Math.min.apply(null, numbers);

// vs. simple loop based algorithm
max = -Infinity;
min = +Infinity;

for (let i = 0; i < numbers.length; i++) {
  if (numbers[i] > max) {
    max = numbers[i];
  }
  if (numbers[i] < min) {
    min = numbers[i];
  }
}
```


But beware: by using `apply()` (or the spread syntax) with an
arbitrarily long arguments list, you run the risk of exceeding the
JavaScript engine\'s argument length limit.

The consequences of calling a function with too many arguments (that is,
more than tens of thousands of arguments) is unspecified and varies
across engines. (The JavaScriptCore engine has a hard-coded [argument
limit of 65536](https://webkit.org/b/80797).) Most engines throw an
exception; but there\'s no normative specification preventing other
behaviors, such as arbitrarily limiting the number of arguments actually
passed to the applied function. To illustrate this latter case: if such
an engine had a limit of four arguments (actual limits are of course
significantly higher), it would be as if the arguments `5, 6, 2, 3` had
been passed to `apply` in the examples above, rather than the full
array.

If your value array might grow into the tens of thousands, use a hybrid
strategy: apply your function to chunks of the array at a time:

 
 
[js]


```js
function minOfArray(arr) {
  let min = Infinity;
  const QUANTUM = 32768;

  for (let i = 0; i < arr.length; i += QUANTUM) {
    const submin = Math.min.apply(
      null,
      arr.slice(i, Math.min(i + QUANTUM, arr.length)),
    );
    min = Math.min(submin, min);
  }

  return min;
}

const min = minOfArray([5, 6, 2, 3, 7]);
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-function.prototype.apply]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-function.prototype.apply)

  ---------------------------------------------------------------------------------------------------------------------------------


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

`generic_arrays_as_arguments`

17

12

4

5

6

18

4

10.1

6

1.0

≤37

1.0

0.10.0

 
See also 
--------

 
-   [`arguments`](../../functions/arguments)
-   [`Function.prototype.bind()`](bind)
-   [`Function.prototype.call()`](call)
-   [`Reflect.apply()`](../reflect/apply)
-   [Functions](../../functions)
-   [Spread syntax (`...`)](../../operators/spread_syntax)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply>

