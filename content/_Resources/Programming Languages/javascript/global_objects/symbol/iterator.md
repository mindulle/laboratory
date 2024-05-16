Symbol.iterator
===============

 
The `Symbol.iterator` static data property represents the [well-known
symbol](../symbol#well-known_symbols) `@@iterator`. The [iterable
protocol](../../iteration_protocols#the_iterable_protocol) looks up this
symbol for the method that returns the iterator for an object. In order
for an object to be iterable, it must have an `@@iterator` key.


 
Try it 
------

 



 
Value
-----

 
The well-known symbol `@@iterator`.

 
Property attributes of `Symbol.iterator`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
Whenever an object needs to be iterated (such as at the beginning of a
`for...of` loop), its `@@iterator` method is called with no arguments,
and the returned **iterator** is used to obtain the values to be
iterated.

Some built-in types have a default iteration behavior, while other types
(such as [`Object`](../object)) do not. Some built-in types with a
`@@iterator` method are:

-   [`Array.prototype[@@iterator]()`](../array/@@iterator)
-   [`TypedArray.prototype[@@iterator]()`](../typedarray/@@iterator)
-   [`String.prototype[@@iterator]()`](../string/@@iterator)
-   [`Map.prototype[@@iterator]()`](../map/@@iterator)
-   [`Set.prototype[@@iterator]()`](../set/@@iterator)

See also [Iteration protocols](../../iteration_protocols) for more
information.



 
Examples
--------


 
### User-defined iterables 

 
We can make our own iterables like this:

 
 
[js]


```js
const myIterable = {};
myIterable[Symbol.iterator] = function* () {
  yield 1;
  yield 2;
  yield 3;
};
[...myIterable]; // [1, 2, 3]
```


Or iterables can be defined directly inside a class or object using a
[computed
property](../../operators/object_initializer#computed_property_names):

 
 
[js]


```js
class Foo {
  *[Symbol.iterator]() {
    yield 1;
    yield 2;
    yield 3;
  }
}

const someObj = {
  *[Symbol.iterator]() {
    yield "a";
    yield "b";
  },
};

console.log(...new Foo()); // 1, 2, 3
console.log(...someObj); // 'a', 'b'
```




 
### Non-well-formed iterables 

 
If an iterable\'s `@@iterator` method does not return an iterator
object, then it is a non-well-formed iterable. Using it as such is
likely to result in runtime exceptions or buggy behavior:

 
 
[js]


```js
const nonWellFormedIterable = {};
nonWellFormedIterable[Symbol.iterator] = () => 1;
[...nonWellFormedIterable]; // TypeError: [Symbol.iterator]() returned a non-object value
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.iterator]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.iterator)

  ---------------------------------------------------------------------------------------------------------------


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

`iterator`

43

12

36

30

10

43

36

30

10

4.0

43

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `Symbol.iterator` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-symbol)
-   [Iteration protocols](../../iteration_protocols)
-   [`Array.prototype[@@iterator]()`](../array/@@iterator)
-   [`TypedArray.prototype[@@iterator]()`](../typedarray/@@iterator)
-   [`String.prototype[@@iterator]()`](../string/@@iterator)
-   [`Map.prototype[@@iterator]()`](../map/@@iterator)
-   [`Set.prototype[@@iterator]()`](../set/@@iterator)
-   [`arguments[@@iterator]()`](../../functions/arguments/@@iterator)
-   [`Segments.prototype[@@iterator]()`](../intl/segmenter/segment/segments/@@iterator)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/iterator>

