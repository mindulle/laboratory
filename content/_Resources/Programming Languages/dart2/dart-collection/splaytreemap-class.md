[dart:collection](../dart-collection/dart-collection-library){._links-link}

SplayTreeMap\<K, V\> class
==========================

A [Map](../dart-core/map-class) of objects that can be ordered relative
to each other.

The map is based on a self-balancing binary tree. It allows most
single-entry operations in amortized logarithmic time.

Keys of the map are compared using the `compare` function passed in the
constructor, both for ordering and for equality. If the map contains
only the key `a`, then `map.containsKey(b)` will return `true` if and
only if `compare(a, b) == 0`, and the value of `a == b` is not even
checked. If the compare function is omitted, the objects are assumed to
be [Comparable](../dart-core/comparable-class), and are compared using
their [Comparable.compareTo](../dart-core/comparable/compareto) method.
Non-comparable objects (including `null`) will not work as keys in that
case.

To allow calling [operator \[\]](splaytreemap/operator_get),
[remove](splaytreemap/remove) or [containsKey](splaytreemap/containskey)
with objects that are not supported by the `compare` function, an extra
`isValidKey` predicate function can be supplied. This function is tested
before using the `compare` function on an argument value that may not be
a `K` value. If omitted, the `isValidKey` function defaults to testing
if the value is a `K`.

**Notice:** Do not modify a map (add or remove keys) while an operation
is being performed on that map, for example in functions called during a
[forEach](splaytreemap/foreach) or
[putIfAbsent](splaytreemap/putifabsent) call, or while iterating the map
([keys](splaytreemap/keys), [values](splaytreemap/values) or
[entries](splaytreemap/entries)).

Example:

``` {.language-dart data-language="dart"}
final planetsByMass = SplayTreeMap<double, String>((a, b) => a.compareTo(b));
```

To add data to a map, use [operator\[\]=](splaytreemap/operator_put),
[addAll](splaytreemap/addall) or [addEntries](mapmixin/addentries).

``` {.language-dart data-language="dart"}
planetsByMass[0.06] = 'Mercury';
planetsByMass
    .addAll({0.81: 'Venus', 1.0: 'Earth', 0.11: 'Mars', 317.83: 'Jupiter'});
```

To check if the map is empty, use [isEmpty](splaytreemap/isempty) or
[isNotEmpty](splaytreemap/isnotempty). To find the number of map
entries, use [length](splaytreemap/length).

``` {.language-dart data-language="dart"}
print(planetsByMass.isEmpty); // false
print(planetsByMass.length); // 5
```

The [forEach](splaytreemap/foreach) method calls a function for each
key/value entry of the map.

``` {.language-dart data-language="dart"}
planetsByMass.forEach((key, value) {
  print('$key \t $value');
  // 0.06    Mercury
  // 0.11    Mars
  // 0.81    Venus
  // 1.0     Earth
  // 317.83  Jupiter
});
```

To check whether the map has an entry with a specific key, use
[containsKey](splaytreemap/containskey).

``` {.language-dart data-language="dart"}
final keyOneExists = planetsByMass.containsKey(1.0); // true
final keyFiveExists = planetsByMass.containsKey(5); // false
```

To check whether the map has an entry with a specific value, use
[containsValue](splaytreemap/containsvalue).

``` {.language-dart data-language="dart"}
final earthExists = planetsByMass.containsValue('Earth'); // true
final plutoExists = planetsByMass.containsValue('Pluto'); // false
```

To remove an entry with a specific key, use
[remove](splaytreemap/remove).

``` {.language-dart data-language="dart"}
final removedValue = planetsByMass.remove(1.0);
print(removedValue); // Earth
```

To remove multiple entries at the same time, based on their keys and
values, use [removeWhere](mapmixin/removewhere).

``` {.language-dart data-language="dart"}
planetsByMass.removeWhere((key, value) => key <= 1);
print(planetsByMass); // {317.83: Jupiter}
```

To conditionally add or modify a value for a specific key, depending on
whether there already is an entry with that key, use
[putIfAbsent](splaytreemap/putifabsent) or
[update](splaytreemap/update).

``` {.language-dart data-language="dart"}
planetsByMass.update(1, (v) => '', ifAbsent: () => 'Earth');
planetsByMass.putIfAbsent(317.83, () => 'Another Jupiter');
print(planetsByMass); // {1.0: Earth, 317.83: Jupiter}
```

To update the values of all keys, based on the existing key and value,
use [updateAll](splaytreemap/updateall).

``` {.language-dart data-language="dart"}
planetsByMass.updateAll((key, value) => 'X');
print(planetsByMass); // {1.0: X, 317.83: X}
```

To remove all entries and empty the map, use
[clear](splaytreemap/clear).

``` {.language-dart data-language="dart"}
planetsByMass.clear();
print(planetsByMass.isEmpty); // false
print(planetsByMass); // {}
```

**See also:**

-   [Map](../dart-core/map-class), the general interface of key/value
    pair collections.
-   [HashMap](hashmap-class) is unordered (the order of iteration is not
    guaranteed).
-   [LinkedHashMap](linkedhashmap-class) iterates in key insertion
    order.

Mixed in types

:   -   [MapMixin](mapmixin-class)\<K, V\>

Constructors
------------

[SplayTreeMap](splaytreemap/splaytreemap)(\[[int](../dart-core/int-class)
compare(K key1, K key2)?, [bool](../dart-core/bool-class)
isValidKey(dynamic potentialKey)?\])

[SplayTreeMap.from](splaytreemap/splaytreemap.from)([Map](../dart-core/map-class)
other, \[[int](../dart-core/int-class) compare(K key1, K key2)?,
[bool](../dart-core/bool-class) isValidKey(dynamic potentialKey)?\])

::: {.constructor-modifier .features}
factory
:::

Creates a [SplayTreeMap](splaytreemap-class) that contains all key/value
pairs of `other`.

[SplayTreeMap.fromIterable](splaytreemap/splaytreemap.fromiterable)([Iterable](../dart-core/iterable-class)
iterable, {K key(dynamic element)?, V value(dynamic element)?,
[int](../dart-core/int-class) compare(K key1, K key2)?,
[bool](../dart-core/bool-class) isValidKey(dynamic potentialKey)?})

::: {.constructor-modifier .features}
factory
:::

Creates a [SplayTreeMap](splaytreemap-class) where the keys and values
are computed from the `iterable`.

[SplayTreeMap.fromIterables](splaytreemap/splaytreemap.fromiterables)([Iterable](../dart-core/iterable-class)\<K\>
keys, [Iterable](../dart-core/iterable-class)\<V\> values,
\[[int](../dart-core/int-class) compare(K key1, K key2)?,
[bool](../dart-core/bool-class) isValidKey(dynamic potentialKey)?\])

::: {.constructor-modifier .features}
factory
:::

Creates a [SplayTreeMap](splaytreemap-class) associating the given
`keys` to `values`.

[SplayTreeMap.of](splaytreemap/splaytreemap.of)([Map](../dart-core/map-class)\<K,
V\> other, \[[int](../dart-core/int-class) compare(K key1, K key2)?,
[bool](../dart-core/bool-class) isValidKey(dynamic potentialKey)?\])

::: {.constructor-modifier .features}
factory
:::

Creates a [SplayTreeMap](splaytreemap-class) that contains all key/value
pairs of `other`. Example:

Properties {#instance-properties}
----------

[entries](splaytreemap/entries) →
[Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<K,
V\>\>

::: {.features}
read-only, override
:::

The map entries of [this](splaytreemap-class).

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](splaytreemap/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether there is no key/value pair in the map.

[isNotEmpty](splaytreemap/isnotempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether there is at least one key/value pair in the map.

[keys](splaytreemap/keys) → [Iterable](../dart-core/iterable-class)\<K\>

::: {.features}
read-only, override
:::

The keys of [this](splaytreemap-class).

[length](splaytreemap/length) → [int](../dart-core/int-class)

::: {.features}
read-only, override
:::

The number of key/value pairs in the map.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[values](splaytreemap/values) →
[Iterable](../dart-core/iterable-class)\<V\>

::: {.features}
read-only, override
:::

The values of [this](splaytreemap-class).

Methods {#instance-methods}
-------

[addAll](splaytreemap/addall)([Map](../dart-core/map-class)\<K, V\>
other) → void

::: {.features}
override
:::

Adds all key/value pairs of `other` to this map.

[addEntries](mapmixin/addentries)([Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<K,
V\>\> newEntries) → void

::: {.features}
inherited
:::

Adds all key/value pairs of `newEntries` to this map.

[cast](mapmixin/cast)\<RK, RV\>() → [Map](../dart-core/map-class)\<RK,
RV\>

::: {.features}
inherited
:::

Provides a view of this map as having `RK` keys and `RV` instances, if
necessary.

[clear](splaytreemap/clear)() → void

::: {.features}
override
:::

Removes all entries from the map.

[containsKey](splaytreemap/containskey)([Object](../dart-core/object-class)?
key) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether this map contains the given `key`.

[containsValue](splaytreemap/containsvalue)([Object](../dart-core/object-class)?
value) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether this map contains the given `value`.

[firstKey](splaytreemap/firstkey)() → K?

The first key in the map.

[firstKeyAfter](splaytreemap/firstkeyafter)(K key) → K?

Get the first key in the map that is strictly larger than `key`. Returns
`null` if no key was not found.

[forEach](splaytreemap/foreach)(void f(K key, V value)) → void

::: {.features}
override
:::

Applies `action` to each key/value pair of the map.

[lastKey](splaytreemap/lastkey)() → K?

The last key in the map.

[lastKeyBefore](splaytreemap/lastkeybefore)(K key) → K?

The last key in the map that is strictly smaller than `key`.

[map](mapmixin/map)\<K2,
V2\>([MapEntry](../dart-core/mapentry-class)\<K2, V2\> transform(K key,
V value)) → [Map](../dart-core/map-class)\<K2, V2\>

::: {.features}
inherited
:::

Returns a new map where all entries of this map are transformed by the
given `convert` function.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[putIfAbsent](splaytreemap/putifabsent)(K key, V ifAbsent()) → V

::: {.features}
override
:::

Look up the value of `key`, or add a new entry if it isn\'t there.

[remove](splaytreemap/remove)([Object](../dart-core/object-class)? key)
→ V?

::: {.features}
override
:::

Removes `key` and its associated value, if present, from the map.

[removeWhere](mapmixin/removewhere)([bool](../dart-core/bool-class)
test(K key, V value)) → void

::: {.features}
inherited
:::

Removes all entries of this map that satisfy the given `test`.

[toString](mapmixin/tostring)() → [String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[update](splaytreemap/update)(K key, V update(V value), {V ifAbsent()?})
→ V

::: {.features}
override
:::

Updates the value for the provided `key`.

[updateAll](splaytreemap/updateall)(V update(K key, V value)) → void

::: {.features}
override
:::

Updates all values.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator
\[\]](splaytreemap/operator_get)([Object](../dart-core/object-class)?
key) → V?

::: {.features}
override
:::

The value for the given `key`, or `null` if `key` is not in the map.

[operator \[\]=](splaytreemap/operator_put)(K key, V value) → void

::: {.features}
override
:::

Associates the `key` with the given `value`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeMap-class.html>
:::
