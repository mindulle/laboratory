[dart:collection](../dart-collection/dart-collection-library){._links-link}

HashMap\<K, V\> class
=====================

A hash-table based implementation of [Map](../dart-core/map-class).

The [HashMap](hashmap-class) is unordered (the order of iteration is not
guaranteed).

The keys of a `HashMap` must have consistent
[Object.==](../dart-core/object/operator_equals) and
[Object.hashCode](../dart-core/object/hashcode) implementations. This
means that the `==` operator must define a stable equivalence relation
on the keys (reflexive, symmetric, transitive, and consistent over
time), and that `hashCode` must be the same for objects that are
considered equal by `==`.

Iterating the map\'s keys, values or entries (through
[forEach](../dart-core/map/foreach)) may happen in any order. The
iteration order only changes when the map is modified. Values are
iterated in the same order as their associated keys, so iterating the
[keys](../dart-core/map/keys) and [values](../dart-core/map/values) in
parallel will give matching key and value pairs.

**Notice:** Do not modify a map (add or remove keys) while an operation
is being performed on that map, for example in functions called during a
[forEach](../dart-core/map/foreach) or
[putIfAbsent](../dart-core/map/putifabsent) call, or while iterating the
map ([keys](../dart-core/map/keys), [values](../dart-core/map/values) or
[entries](../dart-core/map/entries)).

Example:

``` {.language-dart data-language="dart"}
final Map<int, String> planets = HashMap(); // Is a HashMap
```

To add data to a map, use
[operator\[\]=](../dart-core/map/operator_put),
[addAll](../dart-core/map/addall) or
[addEntries](../dart-core/map/addentries).

``` {.language-dart data-language="dart"}
planets[3] = 'Earth';
planets.addAll({4: 'Mars'});
final gasGiants = {6: 'Jupiter', 5: 'Saturn'};
planets.addEntries(gasGiants.entries);
print(planets); // fx {5: Saturn, 6: Jupiter, 3: Earth, 4: Mars}
```

To check if the map is empty, use [isEmpty](../dart-core/map/isempty) or
[isNotEmpty](../dart-core/map/isnotempty). To find the number of map
entries, use [length](../dart-core/map/length).

``` {.language-dart data-language="dart"}
final isEmpty = planets.isEmpty; // false
final length = planets.length; // 4
```

The [forEach](../dart-core/map/foreach) iterates through all entries of
a map.

``` {.language-dart data-language="dart"}
planets.forEach((key, value) {
  print('$key \t $value');
  // 5        Saturn
  // 4        Mars
  // 3        Earth
  // 6        Jupiter
});
```

To check whether the map has an entry with a specific key, use
[containsKey](../dart-core/map/containskey).

``` {.language-dart data-language="dart"}
final keyOneExists = planets.containsKey(4); // true
final keyFiveExists = planets.containsKey(1); // false
```

To check whether the map has an entry with a specific value, use
[containsValue](../dart-core/map/containsvalue).

``` {.language-dart data-language="dart"}
final marsExists = planets.containsValue('Mars'); // true
final venusExists = planets.containsValue('Venus'); // false
```

To remove an entry with a specific key, use
[remove](../dart-core/map/remove).

``` {.language-dart data-language="dart"}
final removeValue = planets.remove(5);
print(removeValue); // Jupiter
print(planets); // fx {4: Mars, 3: Earth, 5: Saturn}
```

To remove multiple entries at the same time, based on their keys and
values, use [removeWhere](../dart-core/map/removewhere).

``` {.language-dart data-language="dart"}
planets.removeWhere((key, value) => key == 5);
print(planets); // fx {3: Earth, 4: Mars}
```

To conditionally add or modify a value for a specific key, depending on
whether there already is an entry with that key, use
[putIfAbsent](../dart-core/map/putifabsent) or
[update](../dart-core/map/update).

``` {.language-dart data-language="dart"}
planets.update(4, (v) => 'Saturn');
planets.update(8, (v) => '', ifAbsent: () => 'Neptune');
planets.putIfAbsent(4, () => 'Another Saturn');
print(planets); // fx {4: Saturn, 8: Neptune, 3: Earth}
```

To update the values of all keys, based on the existing key and value,
use [updateAll](../dart-core/map/updateall).

``` {.language-dart data-language="dart"}
planets.updateAll((key, value) => 'X');
print(planets); // fx {8: X, 3: X, 4: X}
```

To remove all entries and empty the map, use
[clear](../dart-core/map/clear).

``` {.language-dart data-language="dart"}
planets.clear();
print(planets); // {}
print(planets.isEmpty); // true
```

**See also:**

-   [Map](../dart-core/map-class), the general interface of key/value
    pair collections.
-   [LinkedHashMap](linkedhashmap-class) iterates in key insertion
    order.
-   [SplayTreeMap](splaytreemap-class) iterates the keys in sorted
    order.

Implemented types

:   -   [Map](../dart-core/map-class)\<K, V\>

Constructors
------------

[HashMap](hashmap/hashmap)({[bool](../dart-core/bool-class) equals(K,
K)?, [int](../dart-core/int-class) hashCode(K)?,
[bool](../dart-core/bool-class) isValidKey(dynamic)?})

::: {.constructor-modifier .features}
factory
:::

Creates an unordered hash-table based [Map](../dart-core/map-class).

[HashMap.from](hashmap/hashmap.from)([Map](../dart-core/map-class)
other)

::: {.constructor-modifier .features}
factory
:::

Creates a [HashMap](hashmap-class) that contains all key/value pairs of
`other`.

[HashMap.fromEntries](hashmap/hashmap.fromentries)([Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<K,
V\>\> entries)

::: {.constructor-modifier .features}
factory
:::

Creates a [HashMap](hashmap-class) containing the entries of `entries`.

[HashMap.fromIterable](hashmap/hashmap.fromiterable)([Iterable](../dart-core/iterable-class)
iterable, {K key(dynamic element)?, V value(dynamic element)?})

::: {.constructor-modifier .features}
factory
:::

Creates a [HashMap](hashmap-class) where the keys and values are
computed from the `iterable`.

[HashMap.fromIterables](hashmap/hashmap.fromiterables)([Iterable](../dart-core/iterable-class)\<K\>
keys, [Iterable](../dart-core/iterable-class)\<V\> values)

::: {.constructor-modifier .features}
factory
:::

Creates a [HashMap](hashmap-class) associating the given `keys` to
`values`.

[HashMap.identity](hashmap/hashmap.identity)()

::: {.constructor-modifier .features}
factory
:::

Creates an unordered identity-based map.

[HashMap.of](hashmap/hashmap.of)([Map](../dart-core/map-class)\<K, V\>
other)

::: {.constructor-modifier .features}
factory
:::

Creates a [HashMap](hashmap-class) that contains all key/value pairs of
`other`. Example:

Properties {#instance-properties}
----------

[entries](../dart-core/map/entries) →
[Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<K,
V\>\>

::: {.features}
read-only, inherited
:::

The map entries of [this](hashmap-class).

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](../dart-core/map/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether there is no key/value pair in the map.

[isNotEmpty](../dart-core/map/isnotempty) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether there is at least one key/value pair in the map.

[keys](../dart-core/map/keys) →
[Iterable](../dart-core/iterable-class)\<K\>

::: {.features}
read-only, inherited
:::

The keys of [this](hashmap-class).

[length](../dart-core/map/length) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The number of key/value pairs in the map.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[values](../dart-core/map/values) →
[Iterable](../dart-core/iterable-class)\<V\>

::: {.features}
read-only, inherited
:::

The values of [this](hashmap-class).

Methods {#instance-methods}
-------

[addAll](../dart-core/map/addall)([Map](../dart-core/map-class)\<K, V\>
other) → void

::: {.features}
inherited
:::

Adds all key/value pairs of `other` to this map.

[addEntries](../dart-core/map/addentries)([Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<K,
V\>\> newEntries) → void

::: {.features}
inherited
:::

Adds all key/value pairs of `newEntries` to this map.

[cast](../dart-core/map/cast)\<RK, RV\>() →
[Map](../dart-core/map-class)\<RK, RV\>

::: {.features}
inherited
:::

Provides a view of this map as having `RK` keys and `RV` instances, if
necessary.

[clear](../dart-core/map/clear)() → void

::: {.features}
inherited
:::

Removes all entries from the map.

[containsKey](../dart-core/map/containskey)([Object](../dart-core/object-class)?
key) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether this map contains the given `key`.

[containsValue](../dart-core/map/containsvalue)([Object](../dart-core/object-class)?
value) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether this map contains the given `value`.

[forEach](../dart-core/map/foreach)(void action(K key, V value)) → void

::: {.features}
inherited
:::

Applies `action` to each key/value pair of the map.

[map](../dart-core/map/map)\<K2,
V2\>([MapEntry](../dart-core/mapentry-class)\<K2, V2\> convert(K key, V
value)) → [Map](../dart-core/map-class)\<K2, V2\>

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

[putIfAbsent](../dart-core/map/putifabsent)(K key, V ifAbsent()) → V

::: {.features}
inherited
:::

Look up the value of `key`, or add a new entry if it isn\'t there.

[remove](../dart-core/map/remove)([Object](../dart-core/object-class)?
key) → V?

::: {.features}
inherited
:::

Removes `key` and its associated value, if present, from the map.

[removeWhere](../dart-core/map/removewhere)([bool](../dart-core/bool-class)
test(K key, V value)) → void

::: {.features}
inherited
:::

Removes all entries of this map that satisfy the given `test`.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[update](../dart-core/map/update)(K key, V update(V value), {V
ifAbsent()?}) → V

::: {.features}
inherited
:::

Updates the value for the provided `key`.

[updateAll](../dart-core/map/updateall)(V update(K key, V value)) → void

::: {.features}
inherited
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
\[\]](../dart-core/map/operator_get)([Object](../dart-core/object-class)?
key) → V?

::: {.features}
inherited
:::

The value for the given `key`, or `null` if `key` is not in the map.

[operator \[\]=](../dart-core/map/operator_put)(K key, V value) → void

::: {.features}
inherited
:::

Associates the `key` with the given `value`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/HashMap-class.html>
:::
