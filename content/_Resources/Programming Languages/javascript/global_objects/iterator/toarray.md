Iterator.prototype.toArray()
============================

 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `toArray()` method of [`Iterator`](../iterator) instances creates a
new [`Array`](../array) instance populated with the elements yielded
from the iterator.


 
Syntax
------

 
 
 
[js]


```js
toArray()
```




 
### Parameters

 
None.



 
### Return value 

 
A new [`Array`](../array) instance containing the elements from the
iterator in the order they were produced.



 
Examples
--------


 
### Using toArray() 

 
`iterator.toArray()` is equivalent to `Array.from(iterator)` and
`[...iterator]`, except that it\'s easier to chain when multiple
iterator helper methods are involved. The following example creates an
iterator that yields terms in the Fibonacci sequence, takes the first 10
terms, filters out the odd numbers, and converts the result to an array:

 
 
[js]


```js
function* fibonacci() {
  let current = 1;
  let next = 1;
  while (true) {
    yield current;
    [current, next] = [next, current + next];
  }
}

const array = fibonacci()
  .take(10)
  .filter((x) => x % 2 === 0)
  .toArray();

console.log(array); // [2, 8, 34]
```


Note that it\'s a good idea to call `toArray()` as a last step of your
processing. For example, `fibonacci().take(10).toArray().filter(...)` is
less efficient, because iterator helpers are lazy and avoids creating a
temporary array.



Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------
  [Iterator Helpers\
  [\#
  sec-iteratorprototype.toarray]](https://tc39.es/proposal-iterator-helpers/#sec-iteratorprototype.toarray)

  -------------------------------------------------------------------------------------------------------------------


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

`toArray`

117

117

No

103

No

117

No

78

No

No

117

No

No

 
See also 
--------

 
-   [Polyfill of `Iterator.prototype.toArray` in
    `core-js`](https://github.com/zloirock/core-js#iterator-helpers)
-   [`Iterator`](../iterator)
-   [`Array.from()`](../array/from)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Iterator/toArray>

