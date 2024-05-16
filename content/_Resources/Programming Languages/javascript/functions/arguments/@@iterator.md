arguments\[@\@iterator\]()
==========================


The `[@@iterator]()` method of [`arguments`](../arguments) objects
implements the [iterable protocol](../../iteration_protocols) and allows
`arguments` objects to be consumed by most syntaxes expecting iterables,
such as the [spread syntax](../../operators/spread_syntax) and
[`for...of`](../../statements/for...of) loops. It returns an [array
iterator object](../../global_objects/iterator) that yields the value of
each index in the `arguments` object.

The initial value of this property is the same function object as the
initial value of the
[`Array.prototype.values`](../../global_objects/array/values) property
(and also the same as
[`Array.prototype[@@iterator]`](../../global_objects/array/@@iterator)).



Syntax
------




[js]


```js
arguments[Symbol.iterator]()
```





### Parameters


None.




### Return value 


The same return value as
[`Array.prototype.values()`](../../global_objects/array/values): a new
[iterable iterator object](../../global_objects/iterator) that yields
the value of each index in the `arguments` object.




Examples
--------



### Iteration using for\...of loop 


Note that you seldom need to call this method directly. The existence of
the `@@iterator` method makes `arguments` objects
[iterable](../../iteration_protocols#the_iterable_protocol), and
iterating syntaxes like the `for...of` loop automatically call this
method to obtain the iterator to loop over.



[js]


```js
function f() {
  for (const letter of arguments) {
    console.log(letter);
  }
}
f("w", "y", "k", "o", "p");
```





### Manually hand-rolling the iterator 


You may still manually call the `next()` method of the returned iterator
object to achieve maximum control over the iteration process.



[js]


```js
function f() {
  const argsIter = arguments[Symbol.iterator]();
  console.log(argsIter.next().value); // a
  console.log(argsIter.next().value); // b
  console.log(argsIter.next().value); // c
  console.log(argsIter.next().value); // d
  console.log(argsIter.next().value); // e
}
f("w", "y", "k", "o", "p");
```




Specifications
--------------


  --------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-createunmappedargumentsobject]](https://tc39.es/ecma262/multipage/ordinary-and-exotic-objects-behaviours.html#sec-createunmappedargumentsobject)

  [ECMAScript Language Specification\
  [\# sec-createmappedargumentsobject]](https://tc39.es/ecma262/multipage/ordinary-and-exotic-objects-behaviours.html#sec-createmappedargumentsobject)
  --------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`@@iterator`

52

12

46

39

9

52

46

41

9

6.0

52

1.0

4.0.0


See also 
--------


-   [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
    guide
-   [Functions](../../functions)
-   [`arguments`](../arguments)
-   [`Array.prototype.values()`](../../global_objects/array/values)
-   [`Symbol.iterator`](../../global_objects/symbol/iterator)
-   [Iteration protocols](../../iteration_protocols)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments/@@iterator>

