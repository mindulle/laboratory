WeakSet
=======

 
A `WeakSet` is a collection of garbage-collectable values, including
objects and [non-registered
symbols](symbol#shared_symbols_in_the_global_symbol_registry). A value
in the `WeakSet` may only occur once. It is unique in the `WeakSet`\'s
collection.


 
Description
-----------

 
Values of WeakSets must be garbage-collectable. Most [primitive data
types](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) can
be arbitrarily created and don\'t have a lifetime, so they cannot be
stored. Objects and [non-registered
symbols](symbol#shared_symbols_in_the_global_symbol_registry) can be
stored because they are garbage-collectable.

The main differences to the [`Set`](set) object are:

-   `WeakSet`s are collections of **objects and symbols only**. They
    cannot contain arbitrary values of any type, as [`Set`](set)s can.
-   The `WeakSet` is *weak*, meaning references to objects in a
    `WeakSet` are held *weakly*. If no other references to a value
    stored in the `WeakSet` exist, those values can be garbage
    collected.
     
    **Note:** This also means that there is no list of current values
    stored in the collection. `WeakSets` are not enumerable.
    



 
### Use case: Detecting circular references 

 
Functions that call themselves recursively need a way of guarding
against circular data structures by tracking which objects have already
been processed.

`WeakSet`s are ideal for this purpose:

 
 
[js]


```js
// Execute a callback on everything stored inside an object
function execRecursively(fn, subject, _refs = new WeakSet()) {
  // Avoid infinite recursion
  if (_refs.has(subject)) {
    return;
  }

  fn(subject);
  if (typeof subject === "object" && subject) {
    _refs.add(subject);
    for (const key in subject) {
      execRecursively(fn, subject[key], _refs);
    }
    _refs.delete(subject);
  }
}

const foo = {
  foo: "Foo",
  bar: {
    bar: "Bar",
  },
};

foo.bar.baz = foo; // Circular reference!
execRecursively((obj) => console.log(obj), foo);
```


Here, a `WeakSet` is created on the first run, and passed along with
every subsequent function call (using the internal `_refs` parameter).

The number of objects or their traversal order is immaterial, so a
`WeakSet` is more suitable (and performant) than a [`Set`](set) for
tracking object references, especially if a very large number of objects
is involved.



 
Constructor
-----------

 

[`WeakSet()`](weakset/weakset)

:   Creates a new `WeakSet` object.



 
Instance properties 
-------------------

 
These properties are defined on `WeakSet.prototype` and shared by all
`WeakSet` instances.

[`WeakSet.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `WeakSet` instances, the initial value is the
    [`WeakSet`](weakset/weakset) constructor.

[`WeakSet.prototype[@@toStringTag]`](#weakset.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"WeakSet"`. This property is used in
    [`Object.prototype.toString()`](object/tostring).



 
Instance methods 
----------------

 

[`WeakSet.prototype.add()`](weakset/add)

:   Appends `value` to the `WeakSet` object.

[`WeakSet.prototype.delete()`](weakset/delete)

:   Removes `value` from the `WeakSet`. `WeakSet.prototype.has(value)`
    will return `false` afterwards.

[`WeakSet.prototype.has()`](weakset/has)

:   Returns a boolean asserting whether `value` is present in the
    `WeakSet` object or not.



 
Examples
--------


 
### Using the WeakSet object 

 
 
 
[js]


```js
const ws = new WeakSet();
const foo = {};
const bar = {};

ws.add(foo);
ws.add(bar);

ws.has(foo); // true
ws.has(bar); // true

ws.delete(foo); // removes foo from the set
ws.has(foo); // false, foo has been removed
ws.has(bar); // true, bar is retained
```


Note that `foo !== bar`. While they are similar objects, *they are not
**the same object***. And so they are both added to the set.



Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-weakset-objects]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-weakset-objects)

  -------------------------------------------------------------------------------------------------------------


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

`WeakSet`

36

12

34

23

9

36

34

24

9

3.0

37

1.0

0.12.0

`WeakSet`

36

12

34

23

9

36

34

24

9

3.0

37

1.0

0.12.0

`add`

36

12

34

23

9

36

34

24

9

3.0

37

1.0

0.12.0

`delete`

36

12

34

23

9

36

34

24

9

3.0

37

1.0

0.12.0

`has`

36

12

34

23

9

36

34

24

9

3.0

37

1.0

0.12.0

`symbol_as_keys`

108

108

No

94

16.4

108

No

73

16.4

21.0

108

No

No

 
See also 
--------

 
-   [Polyfill of `WeakSet` in
    `core-js`](https://github.com/zloirock/core-js#weakset)
-   [`Map`](map)
-   [`Set`](set)
-   [`WeakMap`](weakmap)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet>

