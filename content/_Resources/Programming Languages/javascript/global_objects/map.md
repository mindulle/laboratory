Map
===

 
The `Map` object holds key-value pairs and remembers the original
insertion order of the keys. Any value (both objects and [primitive
values](https://developer.mozilla.org/en-US/docs/Glossary/Primitive))
may be used as either a key or a value.


 
Try it 
------

 



 
Description
-----------

 
`Map` objects are collections of key-value pairs. A key in the `Map`
**may only occur once**; it is unique in the `Map`\'s collection. A
`Map` object is iterated by key-value pairs --- a
[`for...of`](../statements/for...of) loop returns a 2-member array of
`[key, value]` for each iteration. Iteration happens in *insertion
order*, which corresponds to the order in which each key-value pair was
first inserted into the map by the [`set()`](map/set) method (that is,
there wasn\'t a key with the same value already in the map when `set()`
was called).

The specification requires maps to be implemented \"that, on average,
provide access times that are sublinear on the number of elements in the
collection\". Therefore, it could be represented internally as a hash
table (with O(1) lookup), a search tree (with O(log(N)) lookup), or any
other data structure, as long as the complexity is better than O(N).



 
### Key equality 

 
Value equality is based on the
[SameValueZero](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness#same-value-zero_equality)
algorithm. (It used to use
[SameValue](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness#same-value_equality_using_object.is),
which treated `0` and `-0` as different. Check [browser
compatibility](#browser_compatibility).) This means [`NaN`](nan) is
considered the same as `NaN` (even though `NaN !== NaN`) and all other
values are considered equal according to the semantics of the `===`
operator.



 
### Objects vs. Maps 

 
[`Object`](object) is similar to `Map`---both let you set keys to
values, retrieve those values, delete keys, and detect whether something
is stored at a key. For this reason (and because there were no built-in
alternatives), `Object` has been used as `Map` historically.

However, there are important differences that make `Map` preferable in
some cases:

 
+-----------------------+-----------------------+-----------------------+
|                       | Map                   | Object                |
+=======================+=======================+=======================+
| Accidental Keys       | A `Map` does not      | An `Object` has a     |
|                       | contain any keys by   | prototype, so it      |
|                       | default. It only      | contains default keys |
|                       | contains what is      | that could collide    |
|                       | explicitly put into   | with your own keys if |
|                       | it.                   | you\'re not careful.  |
|                       |                       |                       |
|                       |                       |                |
|                       |                       |  |
|                       |                       | **Note:** This can be |
|                       |                       | bypassed by using     |
|                       |                       | [`Object.create(nu    |
|                       |                       | ll)`](object/create), |
|                       |                       | but this is seldom    |
|                       |                       | done.                 |
|                       |                       |                    |
+-----------------------+-----------------------+-----------------------+
| Security              | A `Map` is safe to    | Setting user-provided |
|                       | use with              | key-value pairs on an |
|                       | user-provided keys    | `Object` may allow an |
|                       | and values.           | attacker to override  |
|                       |                       | the object\'s         |
|                       |                       | prototype, which can  |
|                       |                       | lead to [object       |
|                       |                       | injection             |
|                       |                       | attacks](https://git  |
|                       |                       | hub.com/eslint-commun |
|                       |                       | ity/eslint-plugin-sec |
|                       |                       | urity/blob/main/docs/ |
|                       |                       | the-dangers-of-square |
|                       |                       | -bracket-notation.md) |
|                       |                       | . Like the accidental |
|                       |                       | keys issue, this can  |
|                       |                       | also be mitigated by  |
|                       |                       | using a               |
|                       |                       | `null`-prototype      |
|                       |                       | object.               |
+-----------------------+-----------------------+-----------------------+
| Key Types             | A `Map`\'s keys can   | The keys of an        |
|                       | be any value          | `Object` must be      |
|                       | (including functions, | either a              |
|                       | objects, or any       | [`String`](string) or |
|                       | primitive).           | a [`Symbol`](symbol). |
+-----------------------+-----------------------+-----------------------+
| Key Order             | The keys in `Map` are | Although the keys of  |
|                       | ordered in a simple,  | an ordinary `Object`  |
|                       | straightforward way:  | are ordered now, this |
|                       | A `Map` object        | was not always the    |
|                       | iterates entries,     | case, and the order   |
|                       | keys, and values in   | is complex. As a      |
|                       | the order of entry    | result, it\'s best    |
|                       | insertion.            | not to rely on        |
|                       |                       | property order.       |
|                       |                       |                       |
|                       |                       | The order was first   |
|                       |                       | defined for own       |
|                       |                       | properties only in    |
|                       |                       | ECMAScript 2015;      |
|                       |                       | ECMAScript 2020       |
|                       |                       | defines order for     |
|                       |                       | inherited properties  |
|                       |                       | as well. But note     |
|                       |                       | that no single        |
|                       |                       | mechanism iterates    |
|                       |                       | **all** of an         |
|                       |                       | object\'s properties; |
|                       |                       | the various           |
|                       |                       | mechanisms each       |
|                       |                       | include different     |
|                       |                       | subsets of            |
|                       |                       | properties.           |
|                       |                       | ([`for-in`](..        |
|                       |                       | /statements/for...in) |
|                       |                       | includes only         |
|                       |                       | enumerable            |
|                       |                       | string-keyed          |
|                       |                       | properties;           |
|                       |                       | [`Objec               |
|                       |                       | t.keys`](object/keys) |
|                       |                       | includes only own,    |
|                       |                       | enumerable,           |
|                       |                       | string-keyed          |
|                       |                       | properties;           |
|                       |                       | [`Object.getOwnP      |
|                       |                       | ropertyNames`](object |
|                       |                       | /getownpropertynames) |
|                       |                       | includes own,         |
|                       |                       | string-keyed          |
|                       |                       | properties even if    |
|                       |                       | non-enumerable;       |
|                       |                       | [`Object.getOwnPrope  |
|                       |                       | rtySymbols`](object/g |
|                       |                       | etownpropertysymbols) |
|                       |                       | does the same for     |
|                       |                       | just `Symbol`-keyed   |
|                       |                       | properties, etc.)     |
+-----------------------+-----------------------+-----------------------+
| Size                  | The number of items   | Determining the       |
|                       | in a `Map` is easily  | number of items in an |
|                       | retrieved from its    | `Object` is more      |
|                       | [`size`](map/size)    | roundabout and less   |
|                       | property.             | efficient. A common   |
|                       |                       | way to do it is       |
|                       |                       | through the           |
|                       |                       | [`l                   |
|                       |                       | ength`](array/length) |
|                       |                       | of the array returned |
|                       |                       | from                  |
|                       |                       | [`Object.k            |
|                       |                       | eys()`](object/keys). |
+-----------------------+-----------------------+-----------------------+
| Iteration             | A `Map` is an         | `Object` does not     |
|                       | [iterable](../        | implement an          |
|                       | iteration_protocols), | [iteration            |
|                       | so it can be directly | protocol](../i        |
|                       | iterated.             | teration_protocols#th |
|                       |                       | e_iterable_protocol), |
|                       |                       | and so objects are    |
|                       |                       | not directly iterable |
|                       |                       | using the JavaScript  |
|                       |                       | [for\...of](..        |
|                       |                       | /statements/for...of) |
|                       |                       | statement (by         |
|                       |                       | default).             |
|                       |                       |                       |
|                       |                       |                 |
|                       |                       |  |
|                       |                       | **Note:**             |
|                       |                       |                       |
|                       |                       | -   An object can     |
|                       |                       |     implement the     |
|                       |                       |     iteration         |
|                       |                       |     protocol, or you  |
|                       |                       |     can get an        |
|                       |                       |     iterable for an   |
|                       |                       |     object using      |
|                       |                       |     [`Objec           |
|                       |                       | t.keys`](object/keys) |
|                       |                       |     or                |
|                       |                       |     [`Object.entri    |
|                       |                       | es`](object/entries). |
|                       |                       | -   The               |
|                       |                       |     [for\...in](..    |
|                       |                       | /statements/for...in) |
|                       |                       |     statement allows  |
|                       |                       |     you to iterate    |
|                       |                       |     over the          |
|                       |                       |     *enumerable*      |
|                       |                       |     properties of an  |
|                       |                       |     object.           |
|                       |                       |                    |
+-----------------------+-----------------------+-----------------------+
| Performance           | Performs better in    | Not optimized for     |
|                       | scenarios involving   | frequent additions    |
|                       | frequent additions    | and removals of       |
|                       | and removals of       | key-value pairs.      |
|                       | key-value pairs.      |                       |
+-----------------------+-----------------------+-----------------------+
| Serialization and     | No native support for | Native support for    |
| parsing               | serialization or      | serialization from    |
|                       | parsing.              | [`Object`](object) to |
|                       |                       | JSON, using           |
|                       | (But you can build    | [`JSON.stringify      |
|                       | your own              | ()`](json/stringify). |
|                       | serialization and     |                       |
|                       | parsing support for   | Native support for    |
|                       | `Map` by using        | parsing from JSON to  |
|                       | [`JSON.stringif       | [`Object`](object),   |
|                       | y()`](json/stringify) | using                 |
|                       | with its *replacer*   | [`JSON.p              |
|                       | argument, and by      | arse()`](json/parse). |
|                       | using                 |                       |
|                       | [`JSON.               |                       |
|                       | parse()`](json/parse) |                       |
|                       | with its *reviver*    |                       |
|                       | argument. See the     |                       |
|                       | Stack Overflow        |                       |
|                       | question [How do you  |                       |
|                       | JSON.stringify an ES6 |                       |
|                       | Map?                  |                       |
|                       | ](https://stackoverfl |                       |
|                       | ow.com/q/29085197/)). |                       |
+-----------------------+-----------------------+-----------------------+




 
### Setting object properties 

 
Setting Object properties works for Map objects as well, and can cause
considerable confusion.

Therefore, this appears to work in a way:

 
 
[js]


```js
const wrongMap = new Map();
wrongMap["bla"] = "blaa";
wrongMap["bla2"] = "blaaa2";

console.log(wrongMap); // Map { bla: 'blaa', bla2: 'blaaa2' }
```


But that way of setting a property does not interact with the Map data
structure. It uses the feature of the generic object. The value of
\'bla\' is not stored in the Map for queries. Other operations on the
data fail:

 
 
[js]


```js
wrongMap.has("bla"); // false
wrongMap.delete("bla"); // false
console.log(wrongMap); // Map { bla: 'blaa', bla2: 'blaaa2' }
```


The correct usage for storing data in the Map is through the
`set(key, value)` method.

 
 
[js]


```js
const contacts = new Map();
contacts.set("Jessie", { phone: "213-555-1234", address: "123 N 1st Ave" });
contacts.has("Jessie"); // true
contacts.get("Hilary"); // undefined
contacts.set("Hilary", { phone: "617-555-4321", address: "321 S 2nd St" });
contacts.get("Jessie"); // {phone: "213-555-1234", address: "123 N 1st Ave"}
contacts.delete("Raymond"); // false
contacts.delete("Jessie"); // true
console.log(contacts.size); // 1
```




 
### Map-like browser APIs 

 
`Map` (or \"maplike objects\") are [Web
API](https://developer.mozilla.org/en-US/docs/Web/API) interfaces that
behave in many ways like a `Map`.

Just like `Map`, entries can be iterated in the same order that they
were added to the object. `Map`-like objects and `Map` also have
properties and methods that share the same name and behavior. However
unlike `Map` they only allow specific predefined types for the keys and
values of each entry.

The allowed types are set in the specification IDL definition. For
example,
[`RTCStatsReport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport)
is a `Map`-like object that must use strings for keys and objects for
values. This is defined in the specification IDL below:

 
 
[webidl]


```webidl
interface RTCStatsReport {
  readonly maplike<DOMString, object>;
};
```


`Map`-like objects are either read-only or read-writable (see the
`readonly` keyword in the IDL above).

-   Read-only `Map`-like objects have the property
    [`size`](#map.prototype.size), and the methods:
    [`entries()`](#map.prototype.entries),
    [`forEach()`](#map.prototype.foreach),
    [`get()`](#map.prototype.get), [`has()`](#map.prototype.has),
    [`keys()`](#map.prototype.keys),
    [`values()`](#map.prototype.values), and
    [`@@iterator`](#map.prototypeiterator).
-   Writeable `Map`-like objects additionally have the methods:
    [`clear()`](#map.prototype.clear),
    [`delete()`](#map.prototype.delete), and
    [`set()`](#map.prototype.set).

The methods and properties have the same behavior as the equivalent
entities in `Map`, except for the restriction on the types of the keys
and values.

The following are examples of read-only `Map`-like browser objects:

-   [`AudioParamMap`](https://developer.mozilla.org/en-US/docs/Web/API/AudioParamMap)
-   [`RTCStatsReport`](https://developer.mozilla.org/en-US/docs/Web/API/RTCStatsReport)
-   [`EventCounts`](https://developer.mozilla.org/en-US/docs/Web/API/EventCounts)
-   [`KeyboardLayoutMap`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardLayoutMap)
-   [`MIDIInputMap`](https://developer.mozilla.org/en-US/docs/Web/API/MIDIInputMap)
-   [`MIDIOutputMap`](https://developer.mozilla.org/en-US/docs/Web/API/MIDIOutputMap)



 
Constructor
-----------

 

[`Map()`](map/map)

:   Creates a new `Map` object.



 
Static properties 
-----------------

 

[`Map[@@species]`](map/@@species)

:   The constructor function that is used to create derived objects.



 
Static methods 
--------------

 

[`Map.groupBy()`](map/groupby)

:   Groups the elements of a given iterable using the values returned by
    a provided callback function. The final returned `Map` uses the
    unique values from the test function as keys, which can be used to
    get the array of elements in each group.



 
Instance properties 
-------------------

 
These properties are defined on `Map.prototype` and shared by all `Map`
instances.

[`Map.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For `Map`
    instances, the initial value is the [`Map`](map/map) constructor.

[`Map.prototype.size`](map/size)

:   Returns the number of key/value pairs in the `Map` object.

[`Map.prototype[@@toStringTag]`](#map.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"Map"`. This property is used in
    [`Object.prototype.toString()`](object/tostring).



 
Instance methods 
----------------

 

[`Map.prototype.clear()`](map/clear)

:   Removes all key-value pairs from the `Map` object.

[`Map.prototype.delete()`](map/delete)

:   Returns `true` if an element in the `Map` object existed and has
    been removed, or `false` if the element does not exist.
    `map.has(key)` will return `false` afterwards.

[`Map.prototype.entries()`](map/entries)

:   Returns a new Iterator object that contains a two-member array of
    `[key, value]` for each element in the `Map` object in insertion
    order.

[`Map.prototype.forEach()`](map/foreach)

:   Calls `callbackFn` once for each key-value pair present in the `Map`
    object, in insertion order. If a `thisArg` parameter is provided to
    `forEach`, it will be used as the `this` value for each callback.

[`Map.prototype.get()`](map/get)

:   Returns the value associated to the passed key, or `undefined` if
    there is none.

[`Map.prototype.has()`](map/has)

:   Returns a boolean indicating whether a value has been associated
    with the passed key in the `Map` object or not.

[`Map.prototype.keys()`](map/keys)

:   Returns a new Iterator object that contains the keys for each
    element in the `Map` object in insertion order.

[`Map.prototype.set()`](map/set)

:   Sets the value for the passed key in the `Map` object. Returns the
    `Map` object.

[`Map.prototype.values()`](map/values)

:   Returns a new Iterator object that contains the values for each
    element in the `Map` object in insertion order.

[`Map.prototype[@@iterator]()`](map/@@iterator)

:   Returns a new Iterator object that contains a two-member array of
    `[key, value]` for each element in the `Map` object in insertion
    order.



 
Examples
--------


 
### Using the Map object 

 
 
 
[js]


```js
const myMap = new Map();

const keyString = "a string";
const keyObj = {};
const keyFunc = function () {};

// setting the values
myMap.set(keyString, "value associated with 'a string'");
myMap.set(keyObj, "value associated with keyObj");
myMap.set(keyFunc, "value associated with keyFunc");

console.log(myMap.size); // 3

// getting the values
console.log(myMap.get(keyString)); // "value associated with 'a string'"
console.log(myMap.get(keyObj)); // "value associated with keyObj"
console.log(myMap.get(keyFunc)); // "value associated with keyFunc"

console.log(myMap.get("a string")); // "value associated with 'a string'", because keyString === 'a string'
console.log(myMap.get({})); // undefined, because keyObj !== {}
console.log(myMap.get(function () {})); // undefined, because keyFunc !== function () {}
```




 
### Using NaN as Map keys 

 
[`NaN`](nan) can also be used as a key. Even though every `NaN` is not
equal to itself (`NaN !== NaN` is true), the following example works
because `NaN`s are indistinguishable from each other:

 
 
[js]


```js
const myMap = new Map();
myMap.set(NaN, "not a number");

myMap.get(NaN);
// "not a number"

const otherNaN = Number("foo");
myMap.get(otherNaN);
// "not a number"
```




 
### Iterating Map with for\...of 

 
Maps can be iterated using a `for...of` loop:

 
 
[js]


```js
const myMap = new Map();
myMap.set(0, "zero");
myMap.set(1, "one");

for (const [key, value] of myMap) {
  console.log(`${key} = ${value}`);
}
// 0 = zero
// 1 = one

for (const key of myMap.keys()) {
  console.log(key);
}
// 0
// 1

for (const value of myMap.values()) {
  console.log(value);
}
// zero
// one

for (const [key, value] of myMap.entries()) {
  console.log(`${key} = ${value}`);
}
// 0 = zero
// 1 = one
```




 
### Iterating Map with forEach() 

 
Maps can be iterated using the [`forEach()`](map/foreach) method:

 
 
[js]


```js
myMap.forEach((value, key) => {
  console.log(`${key} = ${value}`);
});
// 0 = zero
// 1 = one
```




 
### Relation with Array objects 

 
 
 
[js]


```js
const kvArray = [
  ["key1", "value1"],
  ["key2", "value2"],
];

// Use the regular Map constructor to transform a 2D key-value Array into a map
const myMap = new Map(kvArray);

console.log(myMap.get("key1")); // "value1"

// Use Array.from() to transform a map into a 2D key-value Array
console.log(Array.from(myMap)); // Will show you exactly the same Array as kvArray

// A succinct way to do the same, using the spread syntax
console.log([...myMap]);

// Or use the keys() or values() iterators, and convert them to an array
console.log(Array.from(myMap.keys())); // ["key1", "key2"]
```




 
### Cloning and merging Maps 

 
Just like `Array`s, `Map`s can be cloned:

 
 
[js]


```js
const original = new Map([[1, "one"]]);

const clone = new Map(original);

console.log(clone.get(1)); // one
console.log(original === clone); // false (useful for shallow comparison)
```


 
**Note:** Keep in mind that *the data itself* is not cloned.


Maps can be merged, maintaining key uniqueness:

 
 
[js]


```js
const first = new Map([
  [1, "one"],
  [2, "two"],
  [3, "three"],
]);

const second = new Map([
  [1, "uno"],
  [2, "dos"],
]);

// Merge two maps. The last repeated key wins.
// Spread syntax essentially converts a Map to an Array
const merged = new Map([...first, ...second]);

console.log(merged.get(1)); // uno
console.log(merged.get(2)); // dos
console.log(merged.get(3)); // three
```


Maps can be merged with Arrays, too:

 
 
[js]


```js
const first = new Map([
  [1, "one"],
  [2, "two"],
  [3, "three"],
]);

const second = new Map([
  [1, "uno"],
  [2, "dos"],
]);

// Merge maps with an array. The last repeated key wins.
const merged = new Map([...first, ...second, [1, "eins"]]);

console.log(merged.get(1)); // eins
console.log(merged.get(2)); // dos
console.log(merged.get(3)); // three
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-map-objects]](https://tc39.es/ecma262/multipage/keyed-collections.html#sec-map-objects)

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

`Map`

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

`Map`

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

`entries`

38

12

20

25

8

38

20

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

`get`

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

`groupBy`

117

117

119

103

16.4--previewpreview

117

119

78

16.4

No

117

1.37

21.0.0

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

20

25

8

38

20

25

8

3.0

38

1.0

0.12.0

`set`

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

`size`

38

12

19From Firefox 13 to Firefox 18, the `size` property was implemented as
a `Map.prototype.size()` method, this has been changed to a property in
later versions conform to the ECMAScript 2015 specification.

25

8

38

19From Firefox 13 to Firefox 18, the `size` property was implemented as
a `Map.prototype.size()` method, this has been changed to a property in
later versions conform to the ECMAScript 2015 specification.

25

8

3.0

38

1.0

0.12.0

`values`

38

12

20

25

8

38

20

25

8

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill for `Map` in
    `core-js`](https://github.com/zloirock/core-js#map)
-   [`Set`](set)
-   [`WeakMap`](weakmap)
-   [`WeakSet`](weakset)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map>

