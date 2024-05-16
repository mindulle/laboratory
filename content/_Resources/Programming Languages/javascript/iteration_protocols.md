Iteration protocols
===================

 
**Iteration protocols** aren\'t new built-ins or syntax, but
*protocols*. These protocols can be implemented by any object by
following some conventions.

There are two protocols: The [iterable protocol](#the_iterable_protocol)
and the [iterator protocol](#the_iterator_protocol).


 
The iterable protocol 
---------------------

 
**The iterable protocol** allows JavaScript objects to define or
customize their iteration behavior, such as what values are looped over
in a [`for...of`](statements/for...of) construct. Some built-in types
are [built-in iterables](#built-in_iterables) with a default iteration
behavior, such as [`Array`](global_objects/array) or
[`Map`](global_objects/map), while other types (such as
[`Object`](global_objects/object)) are not.

In order to be **iterable**, an object must implement the `@@iterator`
method, meaning that the object (or one of the objects up its [prototype
chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain))
must have a property with a `@@iterator` key which is available via
constant [`Symbol.iterator`](global_objects/symbol/iterator):

[`[Symbol.iterator]`](#symbol.iterator)

:   A zero-argument function that returns an object, conforming to the
    [iterator protocol](#the_iterator_protocol).

Whenever an object needs to be iterated (such as at the beginning of a
[`for...of`](statements/for...of) loop), its `@@iterator` method is
called with no arguments, and the returned **iterator** is used to
obtain the values to be iterated.

Note that when this zero-argument function is called, it is invoked as a
method on the iterable object. Therefore inside of the function, the
`this` keyword can be used to access the properties of the iterable
object, to decide what to provide during the iteration.

This function can be an ordinary function, or it can be a generator
function, so that when invoked, an iterator object is returned. Inside
of this generator function, each entry can be provided by using `yield`.



 
The iterator protocol 
---------------------

 
**The iterator protocol** defines a standard way to produce a sequence
of values (either finite or infinite), and potentially a return value
when all values have been generated.

An object is an iterator when it implements a `next()` method with the
following semantics:

[`next()`](#next)

:   A function that accepts zero or one argument and returns an object
    conforming to the `IteratorResult` interface (see below). If a
    non-object value gets returned (such as `false` or `undefined`) when
    a built-in language feature (such as `for...of`) is using the
    iterator, a [`TypeError`](global_objects/typeerror)
    (`"iterator.next() returned a non-object value"`) will be thrown.

All iterator protocol methods (`next()`, `return()`, and `throw()`) are
expected to return an object implementing the `IteratorResult`
interface. It must have the following properties:

[`done`](#done) [Optional]

:   A boolean that\'s `false` if the iterator was able to produce the
    next value in the sequence. (This is equivalent to not specifying
    the `done` property altogether.)

    Has the value `true` if the iterator has completed its sequence. In
    this case, `value` optionally specifies the return value of the
    iterator.

[`value`](#value) [Optional]

:   Any JavaScript value returned by the iterator. Can be omitted when
    `done` is `true`.

In practice, neither property is strictly required; if an object without
either property is returned, it\'s effectively equivalent to
`{ done: false, value: undefined }`.

If an iterator returns a result with `done: true`, any subsequent calls
to `next()` are expected to return `done: true` as well, although this
is not enforced on the language level.

The `next` method can receive a value which will be made available to
the method body. No built-in language feature will pass any value. The
value passed to the `next` method of
[generators](global_objects/generator) will become the value of the
corresponding `yield` expression.

Optionally, the iterator can also implement the `return(value)` and
`throw(exception)` methods, which, when called, tells the iterator that
the caller is done with iterating it and can perform any necessary
cleanup (such as closing database connection).

[`return(value)`](#returnvalue) [Optional]

:   A function that accepts zero or one argument and returns an object
    conforming to the `IteratorResult` interface, typically with `value`
    equal to the `value` passed in and `done` equal to `true`. Calling
    this method tells the iterator that the caller does not intend to
    make any more `next()` calls and can perform any cleanup actions.

[`throw(exception)`](#throwexception) [Optional]

:   A function that accepts zero or one argument and returns an object
    conforming to the `IteratorResult` interface, typically with `done`
    equal to `true`. Calling this method tells the iterator that the
    caller detects an error condition, and `exception` is typically an
    [`Error`](global_objects/error) instance.

 
**Note:** It is not possible to know reflectively (i.e. without actually
calling `next()` and validating the returned result) whether a
particular object implements the iterator protocol.


It is very easy to make an iterator also iterable: just implement an
`[@@iterator]()` method that returns `this`.

 
 
[js]


```js
// Satisfies both the Iterator Protocol and Iterable
const myIterator = {
  next() {
    // ...
  },
  [Symbol.iterator]() {
    return this;
  },
};
```


Such object is called an *iterable iterator*. Doing so allows an
iterator to be consumed by the various syntaxes expecting iterables ---
therefore, it is seldom useful to implement the Iterator Protocol
without also implementing Iterable. (In fact, almost all syntaxes and
APIs expect *iterables*, not *iterators*.) The [generator
object](global_objects/generator) is an example:

 
 
[js]


```js
const aGeneratorObject = (function* () {
  yield 1;
  yield 2;
  yield 3;
})();

console.log(typeof aGeneratorObject.next);
// "function" — it has a next method (which returns the right result), so it's an iterator

console.log(typeof aGeneratorObject[Symbol.iterator]);
// "function" — it has an @@iterator method (which returns the right iterator), so it's an iterable

console.log(aGeneratorObject[Symbol.iterator]() === aGeneratorObject);
// true — its @@iterator method returns itself (an iterator), so it's an iterable iterator
```


All built-in iterators inherit from
[`Iterator.prototype`](global_objects/iterator), which implements the
`[@@iterator]()` method as returning `this`, so that built-in iterators
are also iterable.

However, when possible, it\'s better for `iterable[Symbol.iterator]` to
return different iterators that always start from the beginning, like
[`Set.prototype[@@iterator]()`](global_objects/set/@@iterator) does.



 
The async iterator and async iterable protocols 
-----------------------------------------------

 
There are another pair of protocols used for async iteration, named
**async iterator** and **async iterable** protocols. They have very
similar interfaces compared to the iterable and iterator protocols,
except that each return value from the calls to the iterator methods is
wrapped in a promise.

An object implements the async iterable protocol when it implements the
following methods:

[`[Symbol.asyncIterator]`](global_objects/symbol/asynciterator)

:   A zero-argument function that returns an object, conforming to the
    async iterator protocol.

An object implements the async iterator protocol when it implements the
following methods:

[`next()`](#next_2)

:   A function that accepts zero or one argument and returns a promise.
    The promise fulfills to an object conforming to the `IteratorResult`
    interface, and the properties have the same semantics as those of
    the sync iterator\'s.

[`return(value)`](#returnvalue_2) [Optional]

:   A function that accepts zero or one argument and returns a promise.
    The promise fulfills to an object conforming to the `IteratorResult`
    interface, and the properties have the same semantics as those of
    the sync iterator\'s.

[`throw(exception)`](#throwexception_2) [Optional]

:   A function that accepts zero or one argument and returns a promise.
    The promise fulfills to an object conforming to the `IteratorResult`
    interface, and the properties have the same semantics as those of
    the sync iterator\'s.



 
Interactions between the language and iteration protocols 
---------------------------------------------------------

 
The language specifies APIs that either produce or consume iterables and
iterators.



 
### Built-in iterables 

 
[`String`](global_objects/string), [`Array`](global_objects/array),
[`TypedArray`](global_objects/typedarray), [`Map`](global_objects/map),
[`Set`](global_objects/set), and
[`Segments`](global_objects/intl/segmenter/segment/segments) (returned
by
[`Intl.Segmenter.prototype.segment()`](global_objects/intl/segmenter/segment))
are all built-in iterables, because each of their `prototype` objects
implements an `@@iterator` method. In addition, the
[`arguments`](functions/arguments) object and some DOM collection types
such as
[`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)
are also iterables. There is no object in the core JavaScript language
that is async iterable. Some web APIs, such as
[`ReadableStream`](https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream),
have the `Symbol.asyncIterator` method set by default.

[Generator functions](statements/function*) return [generator
objects](global_objects/generator), which are iterable iterators. [Async
generator functions](statements/async_function*) return [async generator
objects](global_objects/asyncgenerator), which are async iterable
iterators.

The iterators returned from built-in iterables actually all inherit from
a common class [`Iterator`](global_objects/iterator), which implements
the aforementioned `[Symbol.iterator]() { return this; }` method, making
them all iterable iterators. The `Iterator` class also provides
additional [helper methods](global_objects/iterator#iterator_helpers) in
addition to the `next()` method required by the iterator protocol. You
can inspect an iterator\'s prototype chain by logging it in a graphical
console.

```text
console.log([][Symbol.iterator]());

Array Iterator {}
  [[Prototype]]: Array Iterator     ==> This is the prototype shared by all array iterators
    next: ƒ next()
    Symbol(Symbol.toStringTag): "Array Iterator"
    [[Prototype]]: Object           ==> This is the prototype shared by all built-in iterators
      Symbol(Symbol.iterator): ƒ [Symbol.iterator]()
      [[Prototype]]: Object         ==> This is Object.prototype
```



 
### Built-in APIs accepting iterables 

 
There are many APIs that accept iterables. Some examples include:

-   [`Map()`](global_objects/map/map)
-   [`WeakMap()`](global_objects/weakmap/weakmap)
-   [`Set()`](global_objects/set/set)
-   [`WeakSet()`](global_objects/weakset/weakset)
-   [`Promise.all()`](global_objects/promise/all)
-   [`Promise.allSettled()`](global_objects/promise/allsettled)
-   [`Promise.race()`](global_objects/promise/race)
-   [`Promise.any()`](global_objects/promise/any)
-   [`Array.from()`](global_objects/array/from)
-   [`Object.groupBy()`](global_objects/object/groupby)
-   [`Map.groupBy()`](global_objects/map/groupby)

 
 
[js]


```js
const myObj = {};

new WeakSet(
  (function* () {
    yield {};
    yield myObj;
    yield {};
  })(),
).has(myObj); // true
```




 
### Syntaxes expecting iterables 

 
Some statements and expressions expect iterables, for example the
[`for...of`](statements/for...of) loops, [array and parameter
spreading](operators/spread_syntax), [`yield*`](operators/yield*), and
[array destructuring](operators/destructuring_assignment):

 
 
[js]


```js
for (const value of ["a", "b", "c"]) {
  console.log(value);
}
// "a"
// "b"
// "c"

console.log([..."abc"]); // ["a", "b", "c"]

function* gen() {
  yield* ["a", "b", "c"];
}

console.log(gen().next()); // { value: "a", done: false }

[a, b, c] = new Set(["a", "b", "c"]);
console.log(a); // "a"
```


When built-in syntaxes are iterating an iterator, and the last result\'s
`done` is `false` (i.e. the iterator is able to produce more values) but
no more values are needed, the `return` method will get called if
present. This can happen, for example, if a `break` or `return` is
encountered in a `for...of` loop, or if all identifiers are already
bound in an array destructuring.

 
 
[js]


```js
const obj = {
  [Symbol.iterator]() {
    let i = 0;
    return {
      next() {
        i++;
        console.log("Returning", i);
        if (i === 3) return { done: true, value: i };
        return { done: false, value: i };
      },
      return() {
        console.log("Closing");
        return { done: true };
      },
    };
  },
};

const [a] = obj;
// Returning 1
// Closing

const [b, c, d] = obj;
// Returning 1
// Returning 2
// Returning 3
// Already reached the end (the last call returned `done: true`),
// so `return` is not called

for (const b of obj) {
  break;
}
// Returning 1
// Closing
```


The [`for await...of`](statements/for-await...of) loop and
[`yield*`](operators/yield*) in [async generator
functions](statements/async_function*) (but not [sync generator
functions](statements/function*)) are the only ways to interact with
async iterables. Using `for...of`, array spreading, etc. on an async
iterable that\'s not also a sync iterable (i.e. it has
`[@@asyncIterator]()` but no `[@@iterator]()`) will throw a TypeError: x
is not iterable.



 
### Non-well-formed iterables 

 
If an iterable\'s `@@iterator` method doesn\'t return an iterator
object, then it\'s considered a *non-well-formed* iterable.

Using one is likely to result in runtime errors or buggy behavior:

 
 
[js]


```js
const nonWellFormedIterable = {};
nonWellFormedIterable[Symbol.iterator] = () => 1;
[...nonWellFormedIterable]; // TypeError: [Symbol.iterator]() returned a non-object value
```




 
Examples
--------


 
### User-defined iterables 

 
You can make your own iterables like this:

 
 
[js]


```js
const myIterable = {
  *[Symbol.iterator]() {
    yield 1;
    yield 2;
    yield 3;
  },
};

console.log([...myIterable]); // [1, 2, 3]
```




 
### Simple iterator 

 
Iterators are stateful by nature. If you don\'t define it as a
[generator function](statements/function*) (as the example above shows),
you would likely want to encapsulate the state in a closure.

 
 
[js]


```js
function makeIterator(array) {
  let nextIndex = 0;
  return {
    next() {
      return nextIndex < array.length
        ? {
            value: array[nextIndex++],
            done: false,
          }
        : {
            done: true,
          };
    },
  };
}

const it = makeIterator(["yo", "ya"]);

console.log(it.next().value); // 'yo'
console.log(it.next().value); // 'ya'
console.log(it.next().done); // true
```




 
### Infinite iterator 

 
 
 
[js]


```js
function idMaker() {
  let index = 0;
  return {
    next() {
      return {
        value: index++,
        done: false,
      };
    },
  };
}

const it = idMaker();

console.log(it.next().value); // 0
console.log(it.next().value); // 1
console.log(it.next().value); // 2
// ...
```




 
### Defining an iterable with a generator 

 
 
 
[js]


```js
function* makeSimpleGenerator(array) {
  let nextIndex = 0;
  while (nextIndex < array.length) {
    yield array[nextIndex++];
  }
}

const gen = makeSimpleGenerator(["yo", "ya"]);

console.log(gen.next().value); // 'yo'
console.log(gen.next().value); // 'ya'
console.log(gen.next().done); // true

function* idMaker() {
  let index = 0;
  while (true) {
    yield index++;
  }
}

const it = idMaker();

console.log(it.next().value); // 0
console.log(it.next().value); // 1
console.log(it.next().value); // 2
// ...
```




 
### Defining an iterable with a class 

 
State encapsulation can be done with [](privateProperties.md) as well.

 
 
[js]


```js
class SimpleClass {
  #data;

  constructor(data) {
    this.#data = data;
  }

  [Symbol.iterator]() {
    // Use a new index for each iterator. This makes multiple
    // iterations over the iterable safe for non-trivial cases,
    // such as use of break or nested looping over the same iterable.
    let index = 0;

    return {
      // Note: using an arrow function allows `this` to point to the
      // one of `[@@iterator]()` instead of `next()`
      next: () => {
        if (index < this.#data.length) {
          return { value: this.#data[index++], done: false };
        } else {
          return { done: true };
        }
      },
    };
  }
}

const simple = new SimpleClass([1, 2, 3, 4, 5]);

for (const val of simple) {
  console.log(val); // 1 2 3 4 5
}
```




 
### Overriding built-in iterables 

 
For example, a [`String`](global_objects/string) is a built-in iterable
object:

 
 
[js]


```js
const someString = "hi";
console.log(typeof someString[Symbol.iterator]); // "function"
```


`String`\'s [default iterator](global_objects/string/@@iterator) returns
the string\'s code points one by one:

 
 
[js]


```js
const iterator = someString[Symbol.iterator]();
console.log(`${iterator}`); // "[object String Iterator]"

console.log(iterator.next()); // { value: "h", done: false }
console.log(iterator.next()); // { value: "i", done: false }
console.log(iterator.next()); // { value: undefined, done: true }
```


You can redefine the iteration behavior by supplying our own
`@@iterator`:

 
 
[js]


```js
// need to construct a String object explicitly to avoid auto-boxing
const someString = new String("hi");

someString[Symbol.iterator] = function () {
  return {
    // this is the iterator object, returning a single element (the string "bye")
    next() {
      return this._first
        ? { value: "bye", done: (this._first = false) }
        : { done: true };
    },
    _first: true,
  };
};
```


Notice how redefining `@@iterator` affects the behavior of built-in
constructs that use the iteration protocol:

 
 
[js]


```js
console.log([...someString]); // ["bye"]
console.log(`${someString}`); // "hi"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-iteration]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-iteration)

  -----------------------------------------------------------------------------------------------------------


 
See also 
--------

 
-   [Iterators and
    generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators)
    guide
-   [`function*`](statements/function*)
-   [`Symbol.iterator`](global_objects/symbol/iterator)
-   [`Iterator`](global_objects/iterator)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols>

