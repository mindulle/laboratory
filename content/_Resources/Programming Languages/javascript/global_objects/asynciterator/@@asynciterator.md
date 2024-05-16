AsyncIterator.prototype\[@\@asyncIterator\]()
=============================================


The `[@@asyncIterator]()` method of [`AsyncIterator`](../asynciterator)
instances implements the [async iterable
protocol](../../iteration_protocols#the_async_iterator_and_async_iterable_protocols)
and allows built-in async iterators to be consumed by most syntaxes
expecting async iterables, such as
[`for await...of`](../../statements/for-await...of) loops. It returns
the value of [`this`](../../operators/this), which is the async iterator
object itself.



Try it 
------






Syntax
------




[js]


```js
asyncIterator[Symbol.asyncIterator]()
```





### Parameters


None.




### Return value 


The value of [`this`](../../operators/this), which is the async iterator
object itself.




Examples
--------



### Iteration using for await\...of loop 


Note that you seldom need to call this method directly. The existence of
the `@@asyncIterator` method makes all built-in async iterators [async
iterable](../../iteration_protocols#the_async_iterator_and_async_iterable_protocols),
and iterating syntaxes like the `for await...of` loop automatically
calls this method to obtain the async iterator to loop over.



[js]


```js
const asyncIterator = (async function* () {
  yield 1;
  yield 2;
  yield 3;
})();
(async () => {
  for await (const value of asyncIterator) {
    console.log(value);
  }
})();
// Logs: 1, 2, 3
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-asynciteratorprototype-asynciterator]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-asynciteratorprototype-asynciterator)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`@@asyncIterator`

63

79

57

50

11.1

63

57

46

11.3

8.0

63

1.0

10.0.0


See also 
--------


-   [`for await...of`](../../statements/for-await...of)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncIterator/@@asyncIterator>

