Iterator.prototype\[@\@iterator\]()
===================================

 
The `[@@iterator]()` method of [`Iterator`](../iterator) instances
implements the [iterable protocol](../../iteration_protocols) and allows
built-in iterators to be consumed by most syntaxes expecting iterables,
such as the [spread syntax](../../operators/spread_syntax) and
[`for...of`](../../statements/for...of) loops. It returns the value of
[`this`](../../operators/this), which is the iterator object itself.


 
Syntax
------

 
 
 
[js]


```js
iterator[Symbol.iterator]()
```




 
### Parameters

 
None.



 
### Return value 

 
The value of [`this`](../../operators/this), which is the iterator
object itself.



 
Examples
--------


 
### Iteration using for\...of loop 

 
Note that you seldom need to call this method directly. The existence of
the `@@iterator` method makes built-in iterators
[iterable](../../iteration_protocols#the_iterable_protocol), and
iterating syntaxes like the `for...of` loop automatically call this
method to obtain the iterator to loop over.

 
 
[js]


```js
const arrIterator = [1, 2, 3].values();
for (const value of arrIterator) {
  console.log(value);
}
// Logs: 1, 2, 3
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%iteratorprototype%-@\@iterator]](#)

  -----------------------------------------------------------------------


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

38

12

36

27--36A placeholder property named `@@iterator` is used.

17--27A placeholder property named `iterator` is used.

25

10

38

36

27--36A placeholder property named `@@iterator` is used.

17--27A placeholder property named `iterator` is used.

25

10

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [`Iterator`](../iterator)
-   [`Symbol.iterator`](../symbol/iterator)
-   [Iteration protocols](../../iteration_protocols)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Iterator/@@iterator>

