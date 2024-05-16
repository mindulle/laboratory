Iterator
========

 
An `Iterator` object is an object that conforms to the [iterator
protocol](../iteration_protocols#the_iterator_protocol) by providing a
`next()` method that returns an iterator result object. All built-in
iterators inherit from the `Iterator` class. The `Iterator` class
provides a [`@@iterator`](iterator/@@iterator) method that returns the
iterator object itself, making the iterator also
[iterable](../iteration_protocols#the_iterable_protocol). It also
provides some helper methods for working with iterators.


 
Description
-----------

 
The following are all built-in JavaScript iterators:

-   The *Array Iterator* returned by
    [`Array.prototype.values()`](array/values),
    [`Array.prototype.keys()`](array/keys),
    [`Array.prototype.entries()`](array/entries),
    [`Array.prototype[@@iterator]()`](array/@@iterator),
    [`TypedArray.prototype.values()`](typedarray/values),
    [`TypedArray.prototype.keys()`](typedarray/keys),
    [`TypedArray.prototype.entries()`](typedarray/entries),
    [`TypedArray.prototype[@@iterator]()`](typedarray/@@iterator), and
    [`arguments[@@iterator]()`](../functions/arguments/@@iterator).
-   The *String Iterator* returned by
    [`String.prototype[@@iterator]()`](string/@@iterator).
-   The *Map Iterator* returned by
    [`Map.prototype.values()`](map/values),
    [`Map.prototype.keys()`](map/keys),
    [`Map.prototype.entries()`](map/entries), and
    [`Map.prototype[@@iterator]()`](map/@@iterator).
-   The *Set Iterator* returned by
    [`Set.prototype.values()`](set/values),
    [`Set.prototype.keys()`](set/keys),
    [`Set.prototype.entries()`](set/entries), and
    [`Set.prototype[@@iterator]()`](set/@@iterator).
-   The *RegExp String Iterator* returned by
    [`RegExp.prototype[@@matchAll]()`](regexp/@@matchall) and
    [`String.prototype.matchAll()`](string/matchall).
-   The [`Generator`](generator) object returned by [generator
    functions](../statements/function*).
-   The *Segments Iterator* returned by the
    [`[@@iterator]()`](intl/segmenter/segment/segments/@@iterator)
    method of the [`Segments`](intl/segmenter/segment/segments) object
    returned by
    [`Intl.Segmenter.prototype.segment()`](intl/segmenter/segment).
-   The *Iterator Helper* returned by iterator helper methods such as
    [`Iterator.prototype.filter()`](iterator/filter) and
    [`Iterator.prototype.map()`](iterator/map).

Each of these iterators have a distinct prototype object, which defines
the `next()` method used by the particular iterator. For example, all
string iterator objects inherit from a hidden object
`StringIteratorPrototype`, which has a `next()` method that iterates
this string by code points. `StringIteratorPrototype` also has a
[`@@toStringTag`](symbol/tostringtag) property whose initial value is
the string `"String Iterator"`. This property is used in
[`Object.prototype.toString()`](object/tostring). Similarly, other
iterator prototypes also have their own `@@toStringTag` values, which
are the same as the names given above.

All of these prototype objects inherit from `Iterator.prototype`, which
provides a [`@@iterator`](symbol/iterator) method that returns the
iterator object itself, making the iterator also
[iterable](../iteration_protocols#the_iterable_protocol).



 
### Iterator helpers 

 
 
**Note:** These methods are *iterator* helpers, not *iterable* helpers,
because the only requirement for an object to be iterable is just the
presence of a `@@iterator` method. There is no shared prototype to
install these methods on.


The `Iterator` class itself provides some helper methods for working
with iterators. For example, you may be tempted to do the following:

 
 
[js]


```js
const nameToDeposit = new Map([
  ["Anne", 1000],
  ["Bert", 1500],
  ["Carl", 2000],
]);

const totalDeposit = [...nameToDeposit.values()].reduce((a, b) => a + b);
```


This first converts the iterator returned by
[`Map.prototype.values()`](map/values) to an array, then uses the
[`Array.prototype.reduce()`](array/reduce) method to calculate the sum.
However, this both creates an intermediate array and iterates the array
twice. Instead, you can use the `reduce()` method of the iterator
itself:

 
 
[js]


```js
const totalDeposit = nameToDeposit.values().reduce((a, b) => a + b);
```


This method is more efficient, because it only iterates the iterator
once, without memorizing any intermediate values. Iterator helper
methods are necessary to work with infinite iterators:

 
 
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

const seq = fibonacci();
const firstThreeDigitTerm = seq.find((n) => n >= 100);
```


You cannot convert `seq` to an array, because it is infinite. Instead,
you can use the `find()` method of the iterator itself, which only
iterates `seq` as far as necessary to find the first value that
satisfies the condition.

You will find many iterator methods analogous to array methods, such as:

 
  Iterator method                                      Array method
  ---------------------------------------------------- ----------------------------------------------
  [`Iterator.prototype.every()`](iterator/every)       [`Array.prototype.every()`](array/every)
  [`Iterator.prototype.filter()`](iterator/filter)     [`Array.prototype.filter()`](array/filter)
  [`Iterator.prototype.find()`](iterator/find)         [`Array.prototype.find()`](array/find)
  [`Iterator.prototype.flatMap()`](iterator/flatmap)   [`Array.prototype.flatMap()`](array/flatmap)
  [`Iterator.prototype.forEach()`](iterator/foreach)   [`Array.prototype.forEach()`](array/foreach)
  [`Iterator.prototype.map()`](iterator/map)           [`Array.prototype.map()`](array/map)
  [`Iterator.prototype.reduce()`](iterator/reduce)     [`Array.prototype.reduce()`](array/reduce)
  [`Iterator.prototype.some()`](iterator/some)         [`Array.prototype.some()`](array/some)


[`Iterator.prototype.drop()`](iterator/drop) and
[`Iterator.prototype.take()`](iterator/take) combined are somewhat
analogous to [`Array.prototype.slice()`](array/slice).

Among these methods, [`filter()`](iterator/filter),
[`flatMap()`](iterator/flatmap), [`map()`](iterator/map),
[`drop()`](iterator/drop), and [`take()`](iterator/take) return a new
*Iterator Helper* object. The iterator helper is also an `Iterator`
instance, making the helper methods chainable. All iterator helper
objects inherit from a common prototype object, which implements the
iterator protocol:

[`next()`](#next)

:   Calls the `next()` method of the underlying iterator, applies the
    helper method to the result, and returns the result.

[`return()`](#return)

:   Calls the `return()` method of the underlying iterator, and returns
    the result.

The iterator helper shares the same data source as the underlying
iterator, so iterating the iterator helper causes the underlying
iterator to be iterated as well. There is no way to \"fork\" an iterator
to allow it to be iterated multiple times.

 
 
[js]


```js
const it = [1, 2, 3].values();
const it2 = it.drop(0); // Essentially a copy
console.log(it.next().value); // 1
console.log(it2.next().value); // 2
console.log(it.next().value); // 3
```




 
### Proper iterators 

 
There are two kinds of \"iterators\": objects that conform to the
[iterator protocol](../iteration_protocols#the_iterator_protocol)
(which, at its minimum, only requires the presence of a `next()`
method), and objects that inherit from the `Iterator` class, which enjoy
the helper methods. They do not entail each other --- objects that
inherit from `Iterator` do not automatically become iterators, because
the `Iterator` class does not define a `next()` method. Instead, the
object needs to define a `next()` method itself. A *proper iterator* is
one that both conforms to the iterator protocol and inherits from
`Iterator`, and most code expect iterators to be proper iterators and
iterables to return proper iterators. To create proper iterators, define
a class that extends [`Iterator`](iterator/iterator), or use the
[`Iterator.from()`](iterator/from) method.

 
 
[js]


```js
class MyIterator extends Iterator {
  next() {
    // …
  }
}

const myIterator = Iterator.from({
  next() {
    // …
  },
});
```




 
Constructor
-----------

 

[`Iterator()`](iterator/iterator) [Experimental]

:   Intended to be [extended](../classes/extends) by other classes that
    create iterators. Throws an error when constructed by itself.



 
Static methods 
--------------

 

[`Iterator.from()`](iterator/from) [Experimental]

:   Creates a new `Iterator` object from an iterator or iterable object.



 
Instance properties 
-------------------

 
These properties are defined on `Iterator.prototype` and shared by all
`Iterator` instances.

[`Iterator.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `Iterator` instances, the initial value is the
    [`Iterator`](iterator/iterator) constructor.

[`Iterator.prototype[@@toStringTag]`](#iterator.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"Iterator"`. This property is used in
    [`Object.prototype.toString()`](object/tostring).

     
    **Note:** Unlike the `@@toStringTag` on most built-in classes,
    `Iterator.prototype[@@toStringTag]` is writable for web
    compatibility reasons.
    



 
Instance methods 
----------------

 

[`Iterator.prototype.drop()`](iterator/drop) [Experimental]

:   Returns a new iterator helper that skips the given number of
    elements at the start of this iterator.

[`Iterator.prototype.every()`](iterator/every) [Experimental]

:   Tests whether all elements produced by the iterator pass the test
    implemented by the provided function.

[`Iterator.prototype.filter()`](iterator/filter) [Experimental]

:   Returns a new iterator helper that yields only those elements of the
    iterator for which the provided callback function returns `true`.

[`Iterator.prototype.find()`](iterator/find) [Experimental]

:   Returns the first element produced by the iterator that satisfies
    the provided testing function. If no values satisfy the testing
    function, [`undefined`](undefined) is returned.

[`Iterator.prototype.flatMap()`](iterator/flatmap) [Experimental]

:   Returns a new iterator helper that takes each element in the
    original iterator, runs it through a mapping function, and yields
    elements returned by the mapping function (which are contained in
    another iterator or iterable).

[`Iterator.prototype.forEach()`](iterator/foreach) [Experimental]

:   Executes a provided function once for each element produced by the
    iterator.

[`Iterator.prototype.map()`](iterator/map) [Experimental]

:   Returns a new iterator helper that yields elements of the iterator,
    each transformed by a mapping function.

[`Iterator.prototype.reduce()`](iterator/reduce) [Experimental]

:   Executes a user-supplied \"reducer\" callback function on each
    element produced by the iterator, passing in the return value from
    the calculation on the preceding element. The final result of
    running the reducer across all elements is a single value.

[`Iterator.prototype.some()`](iterator/some) [Experimental]

:   Tests whether at least one element in the iterator passes the test
    implemented by the provided function. It returns a boolean value.

[`Iterator.prototype.take()`](iterator/take) [Experimental]

:   Returns a new iterator helper that yields the given number of
    elements in this iterator and then terminates.

[`Iterator.prototype.toArray()`](iterator/toarray) [Experimental]

:   Creates a new [`Array`](array) instance populated with the elements
    yielded from the iterator.

[`Iterator.prototype[@@iterator]()`](iterator/@@iterator)

:   Returns the iterator object itself. This allows iterator objects to
    also be iterable.



 
Examples
--------


 
### Using an iterator as an iterable 

 
All built-in iterators are also iterable, so you can use them in a
`for...of` loop:

 
 
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
  [\# sec-%iteratorprototype%-object]](#)

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

`Iterator`

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

`Iterator`

38

12

17

25

10

38

17

25

10

3.0

38

1.0

0.12.0

`drop`

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

`every`

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

`filter`

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

`find`

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

`flatMap`

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

`forEach`

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

`from`

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

`map`

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

`reduce`

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

`some`

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

`take`

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

 
-   [Polyfill of `Iterator` in
    `core-js`](https://github.com/zloirock/core-js#iterator-helpers)
-   [`function*`](../statements/function*)
-   [Iteration protocols](../iteration_protocols)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Iterator>

