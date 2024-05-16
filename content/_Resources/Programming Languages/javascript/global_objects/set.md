Set
===

 
The `Set` object lets you store unique values of any type, whether
[primitive
values](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) or
object references.


 
Description
-----------

 
`Set` objects are collections of values. A value in the set **may only
occur once**; it is unique in the set\'s collection. You can iterate
through the elements of a set in insertion order. The *insertion order*
corresponds to the order in which each element was inserted into the set
by the [`add()`](set/add) method successfully (that is, there wasn\'t an
identical element already in the set when `add()` was called).

The specification requires sets to be implemented \"that, on average,
provide access times that are sublinear on the number of elements in the
collection\". Therefore, it could be represented internally as a hash
table (with O(1) lookup), a search tree (with O(log(N)) lookup), or any
other data structure, as long as the complexity is better than O(N).



 
### Value equality 

 
Value equality is based on the
[SameValueZero](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness#same-value-zero_equality)
algorithm. (It used to use
[SameValue](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness#same-value_equality_using_object.is),
which treated `0` and `-0` as different. Check [browser
compatibility](#browser_compatibility).) This means [`NaN`](nan) is
considered the same as `NaN` (even though `NaN !== NaN`) and all other
values are considered equal according to the semantics of the `===`
operator.



 
### Performance

 
The [`has`](set/has) method checks if a value is in the set, using an
approach that is, on average, quicker than testing most of the elements
that have previously been added to the set. In particular, it is, on
average, faster than the [`Array.prototype.includes`](array/includes)
method when an array has a `length` equal to a set\'s `size`.



 
### Set composition 

 
The `Set` object provides some methods that allow you to compose sets
like you would with mathematical operations. These methods include:

{width="200"}

To make them more generalizable, these methods don\'t just accept `Set`
objects, but anything that\'s [set-like](#set-like_objects).



 
### Set-like objects 

 
All [set composition methods](#set_composition) require
[`this`](../operators/this) to be an actual `Set` instance, but their
arguments just need to be set-like. A *set-like object* is an object
that provides the following:

-   A [`size`](set/size) property that contains a number.
-   A [`has()`](set/has) method that takes an element and returns a
    boolean.
-   A [`keys()`](set/keys) method that returns an
    [iterator](../iteration_protocols) of the elements in the set.

For example, [`Map`](map) objects are set-like because they also have
[`size`](map/size), [`has()`](map/has), and [`keys()`](map/keys), so
they behave just like sets of keys when used in set methods:

 
 
[js]


```js
const a = new Set([1, 2, 3]);
const b = new Map([
  [1, "one"],
  [2, "two"],
  [4, "four"],
]);
console.log(a.union(b)); // Set(4) {1, 2, 3, 4}
```


 
**Note:** The set-like protocol invokes the `keys()` method instead of
[`[@@iterator]()`](set/@@iterator) to produce elements. This is to make
maps valid set-like objects, because for maps, the iterator produces
*entries* but the `has()` method takes *keys*.


[Arrays](array) are not set-like because they don\'t have a `has()`
method or the `size` property, and their `keys()` method produces
indices instead of elements. [`WeakSet`](weakset) objects are also not
set-like because they don\'t have a `keys()` method.



 
### Set-like browser APIs 

 
Browser `Set` (or \"setlike objects\") are [Web
API](https://developer.mozilla.org/en-US/docs/Web/API) interfaces that
behave in many ways like a `Set`.

Just like `Set`, elements can be iterated in the same order that they
were added to the object. `Set`-like objects and `Set` also have
properties and methods that share the same name and behavior. However
unlike `Set` they only allow a specific predefined type for each entry.

The allowed types are set in the specification IDL definition. For
example,
[`GPUSupportedFeatures`](https://developer.mozilla.org/en-US/docs/Web/API/GPUSupportedFeatures)
is a `Set`-like object that must use strings as the key/value. This is
defined in the specification IDL below:

 
 
[webidl]


```webidl
interface GPUSupportedFeatures {
  readonly setlike<DOMString>;
};
```


`Set`-like objects are either read-only or read-writable (see the
`readonly` keyword in the IDL above).

-   Read-only `Set`-like objects have the property
    [`size`](#set.prototype.size), and the methods:
    [`entries()`](#set.prototype.entries),
    [`forEach()`](#set.prototype.foreach),
    [`has()`](#set.prototype.has), [`keys()`](#set.prototype.keys),
    [`values()`](#set.prototype.values), and
    [`@@iterator`](#set.prototypeiterator).
-   Writeable `Set`-like objects additionally have the methods:
    [`clear()`](#set.prototype.clear),
    [`delete()`](#set.prototype.delete), and
    [`add()`](#set.prototype.add).

The methods and properties have the same behavior as the equivalent
entities in `Set`, except for the restriction on the types of the entry.

The following are examples of read-only `Set`-like browser objects:

-   [`GPUSupportedFeatures`](https://developer.mozilla.org/en-US/docs/Web/API/GPUSupportedFeatures)
-   [`XRAnchorSet`](https://developer.mozilla.org/en-US/docs/Web/API/XRAnchorSet)

The following are examples of writable `Set`-like browser objects:

-   [`CustomStateSet`](https://developer.mozilla.org/en-US/docs/Web/API/CustomStateSet)
-   [`FontFaceSet`](https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSet)
-   [`Highlight`](https://developer.mozilla.org/en-US/docs/Web/API/Highlight)



 
Constructor
-----------

 

[`Set()`](set/set)

:   Creates a new `Set` object.



 
Static properties 
-----------------

 

[`Set[@@species]`](set/@@species)

:   The constructor function that is used to create derived objects.



 
Instance properties 
-------------------

 
These properties are defined on `Set.prototype` and shared by all `Set`
instances.

[`Set.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For `Set`
    instances, the initial value is the [`Set`](set/set) constructor.

[`Set.prototype.size`](set/size)

:   Returns the number of values in the `Set` object.

[`Set.prototype[@@toStringTag]`](#set.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"Set"`. This property is used in
    [`Object.prototype.toString()`](object/tostring).



 
Instance methods 
----------------

 

[`Set.prototype.add()`](set/add)

:   Inserts a new element with a specified value in to a `Set` object,
    if there isn\'t an element with the same value already in the `Set`.

[`Set.prototype.clear()`](set/clear)

:   Removes all elements from the `Set` object.

[`Set.prototype.delete()`](set/delete)

:   Removes the element associated to the `value` and returns a boolean
    asserting whether an element was successfully removed or not.
    `Set.prototype.has(value)` will return `false` afterwards.

[`Set.prototype.difference()`](set/difference) [Experimental]

:   Takes a set and returns a new set containing elements in this set
    but not in the given set.

[`Set.prototype.entries()`](set/entries)

:   Returns a new iterator object that contains `[value, value]` for
    each element in the `Set` object, in insertion order. This is
    similar to the [`Map`](map) object, so that each entry\'s *key* is
    the same as its *value* for a `Set`.

[`Set.prototype.forEach()`](set/foreach)

:   Calls `callbackFn` once for each value present in the `Set` object,
    in insertion order. If a `thisArg` parameter is provided, it will be
    used as the `this` value for each invocation of `callbackFn`.

[`Set.prototype.has()`](set/has)

:   Returns a boolean asserting whether an element is present with the
    given value in the `Set` object or not.

[`Set.prototype.intersection()`](set/intersection) [Experimental]

:   Takes a set and returns a new set containing elements in both this
    set and the given set.

[`Set.prototype.isDisjointFrom()`](set/isdisjointfrom) [Experimental]

:   Takes a set and returns a boolean indicating if this set has no
    elements in common with the given set.

[`Set.prototype.isSubsetOf()`](set/issubsetof) [Experimental]

:   Takes a set and returns a boolean indicating if all elements of this
    set are in the given set.

[`Set.prototype.isSupersetOf()`](set/issupersetof) [Experimental]

:   Takes a set and returns a boolean indicating if all elements of the
    given set are in this set.

[`Set.prototype.keys()`](set/keys)

:   An alias for [`Set.prototype.values()`](set/values).

[`Set.prototype.symmetricDifference()`](set/symmetricdifference) [Experimental]

:   Takes a set and returns a new set containing elements which are in
    either this set or the given set, but not in both.

[`Set.prototype.union()`](set/union) [Experimental]

:   Takes a set and returns a new set containing elements which are in
    either or both of this set and the given set.

[`Set.prototype.values()`](set/values)

:   Returns a new iterator object that yields the **values** for each
    element in the `Set` object in insertion order.

[`Set.prototype[@@iterator]()`](set/@@iterator)

:   Returns a new iterator object that yields the **values** for each
    element in the `Set` object in insertion order.



 
Examples
--------


 
### Using the Set object 

 
 
 
[js]


```js
const mySet1 = new Set();

mySet1.add(1); // Set(1) { 1 }
mySet1.add(5); // Set(2) { 1, 5 }
mySet1.add(5); // Set(2) { 1, 5 }
mySet1.add("some text"); // Set(3) { 1, 5, 'some text' }
const o = { a: 1, b: 2 };
mySet1.add(o);

mySet1.add({ a: 1, b: 2 }); // o is referencing a different object, so this is okay

mySet1.has(1); // true
mySet1.has(3); // false, since 3 has not been added to the set
mySet1.has(5); // true
mySet1.has(Math.sqrt(25)); // true
mySet1.has("Some Text".toLowerCase()); // true
mySet1.has(o); // true

mySet1.size; // 5

mySet1.delete(5); // removes 5 from the set
mySet1.has(5); // false, 5 has been removed

mySet1.size; // 4, since we just removed one value

mySet1.add(5); // Set(5) { 1, 'some text',  - a previously deleted item will be added as a new item, it will not retain its original position before deletion

console.log(mySet1); // Set(5) { 1, "some text", {…}, {…}, 5 }
```




 
### Iterating sets 

 
The iteration over a set visits elements in insertion order.

 
 
[js]


```js
for (const item of mySet1) {
  console.log(item);
}
// 1, "some text", { "a": 1, "b": 2 }, { "a": 1, "b": 2 }, 5

for (const item of mySet1.keys()) {
  console.log(item);
}
// 1, "some text", { "a": 1, "b": 2 }, { "a": 1, "b": 2 }, 5

for (const item of mySet1.values()) {
  console.log(item);
}
// 1, "some text", { "a": 1, "b": 2 }, { "a": 1, "b": 2 }, 5

// key and value are the same here
for (const [key, value] of mySet1.entries()) {
  console.log(key);
}
// 1, "some text", { "a": 1, "b": 2 }, { "a": 1, "b": 2 }, 5

// Convert Set object to an Array object, with Array.from
const myArr = Array.from(mySet1); // [1, "some text", {"a": 1, "b": 2}, {"a": 1, "b": 2}, 5]

// the following will also work if run in an HTML document
mySet1.add(document.body);
mySet1.has(document.querySelector("body")); // true

// converting between Set and Array
const mySet2 = new Set([1, 2, 3, 4]);
console.log(mySet2.size); // 4
console.log([...mySet2]); // [1, 2, 3, 4]

// intersect can be simulated via
const intersection = new Set([...mySet1].filter((x) => mySet2.has(x)));

// difference can be simulated via
const difference = new Set([...mySet1].filter((x) => !mySet2.has(x)));

// Iterate set entries with forEach()
mySet2.forEach((value) => {
  console.log(value);
});
// 1
// 2
// 3
// 4
```




 
### Implementing basic set operations 

 
 
 
[js]


```js
function isSuperset(set, subset) {
  for (const elem of subset) {
    if (!set.has(elem)) {
      return false;
    }
  }
  return true;
}

function union(setA, setB) {
  const _union = new Set(setA);
  for (const elem of setB) {
    _union.add(elem);
  }
  return _union;
}

function intersection(setA, setB) {
  const _intersection = new Set();
  for (const elem of setB) {
    if (setA.has(elem)) {
      _intersection.add(elem);
    }
  }
  return _intersection;
}

function symmetricDifference(setA, setB) {
  const _difference = new Set(setA);
  for (const elem of setB) {
    if (_difference.has(elem)) {
      _difference.delete(elem);
    } else {
      _difference.add(elem);
    }
  }
  return _difference;
}

function difference(setA, setB) {
  const _difference = new Set(setA);
  for (const elem of setB) {
    _difference.delete(elem);
  }
  return _difference;
}

// Examples
const setA = new Set([1, 2, 3, 4]);
const setB = new Set([2, 3]);
const setC = new Set([3, 4, 5, 6]);

isSuperset(setA, setB); // returns true
union(setA, setC); // returns Set {1, 2, 3, 4, 5, 6}
intersection(setA, setC); // returns Set {3, 4}
symmetricDifference(setA, setC); // returns Set {1, 2, 5, 6}
difference(setA, setC); // returns Set {1, 2}
```




 
### Relation to arrays 

 
 
 
[js]


```js
const myArray = ["value1", "value2", "value3"];

// Use the regular Set constructor to transform an Array into a Set
const mySet = new Set(myArray);

mySet.has("value1"); // returns true

// Use the spread syntax to transform a set into an Array.
console.log([...mySet]); // Will show you exactly the same Array as myArray
```




 
### Remove duplicate elements from an array 

 
 
 
[js]


```js
// Use to remove duplicate elements from an array
const numbers = [2, 13, 4, 4, 2, 13, 13, 4, 4, 5, 5, 6, 6, 7, 5, 32, 13, 4, 5];

console.log([...new Set(numbers)]); // [2, 13, 4, 5, 6, 7, 32]
```




 
### Relation to strings 

 
 
 
[js]


```js
// Case sensitive (set will contain "F" and "f")
new Set("Firefox"); // Set(7) [ "F", "i", "r", "e", "f", "o", "x" ]

// Duplicate omission ("f" occurs twice in the string but set will contain only one)
new Set("firefox"); // Set(6) [ "f", "i", "r", "e", "o", "x" ]
```




 
### Use a set to ensure the uniqueness of a list of values 

 
 
 
[js]


```js
const array = Array.from(document.querySelectorAll("[id]")).map((e) => e.id);

const set = new Set(array);
console.assert(set.size === array.length);
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-set-objects]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-set-objects)

  -----------------------------------------------------------------------------------------------------


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

43

12

36

27--36A placeholder property named `@@iterator` is used.

17--27A placeholder property named `iterator` is used.

30

9

43

36

27--36A placeholder property named `@@iterator` is used.

17--27A placeholder property named `iterator` is used.

30

9

4.0

43

1.0

0.12.0

`@@species`

51

13

41

38

10

51

41

41

10

5.0

51

1.0

6.5.0

`Set`

38

12

13

25

8

38

14

25

8

3.0

38

1.0

0.12.0

`Set`

38

12

13

25

8

38

14

25

8

3.0

38

1.0

0.12.0

`add`

38

12

13

25

8

38

14

25

8

3.0

38

1.0

0.12.0

`clear`

38

12

19

25

8

38

19

25

8

3.0

38

1.0

0.12.0

`delete`

38

12

13

25

8

38

14

25

8

3.0

38

1.0

0.12.0

`difference`

No

No

preview

No

17

No

No

No

17

No

No

No

No

`entries`

38

12

24

25

8

38

24

25

8

3.0

38

1.0

0.12.0

`forEach`

38

12

25

25

8

38

25

25

8

3.0

38

1.0

0.12.0

`has`

38

12

13

25

8

38

14

25

8

3.0

38

1.0

0.12.0

`intersection`

No

No

preview

No

17

No

No

No

17

No

No

No

No

`isDisjointFrom`

No

No

preview

No

17

No

No

No

17

No

No

No

No

`isSubsetOf`

No

No

preview

No

17

No

No

No

17

No

No

No

No

`isSupersetOf`

No

No

preview

No

17

No

No

No

17

No

No

No

No

`key_equality_for_zeros`

38

12

29

25

9

38

29

25

9

3.0

38

1.0

4.0.0

`keys`

38

12

24

25

8

38

24

25

8

3.0

38

1.0

0.12.0

`size`

38

12

19From Firefox 13 to Firefox 18, the `size` property was implemented as
a `Set.prototype.size()` method, this has been changed to a property in
later versions conform to the ECMAScript 2015 specification.

25

8

38

19From Firefox 13 to Firefox 18, the `size` property was implemented as
a `Set.prototype.size()` method, this has been changed to a property in
later versions conform to the ECMAScript 2015 specification.

25

8

3.0

38

1.0

0.12.0

`symmetricDifference`

No

No

preview

No

17

No

No

No

17

No

No

No

No

`union`

No

No

preview

No

17

No

No

No

17

No

No

No

No

`values`

38

12

24

25

8

38

24

25

8

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `Set` in
    `core-js`](https://github.com/zloirock/core-js#set)
-   [`Map`](map)
-   [`WeakMap`](weakmap)
-   [`WeakSet`](weakset)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set>

