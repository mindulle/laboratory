[dart:collection](../dart-collection/dart-collection-library){._links-link}

LinkedHashMap\<K, V\> class
===========================

An insertion-ordered [Map](../dart-core/map-class) with expected
constant-time lookup.

A non-constant map literal, like `{"a": 42, "b": 7}`, is a
`LinkedHashMap`.

The [keys](../dart-core/map/keys), [values](../dart-core/map/values) and
[entries](../dart-core/map/entries) are iterated in key insertion order.

The map uses a hash-table to look up entries, so keys must have suitable
implementations of
[Object.operator==](../dart-core/object/operator_equals) and
[Object.hashCode](../dart-core/object/hashcode). If the hash codes are
not well-distributed, the performance of map operations may suffer.

The insertion order of keys is remembered, and keys are iterated in the
order they were inserted into the map. Values and entries are iterated
in their corresponding key\'s order. Changing a key\'s value, when the
key is already in the map, does not change the iteration order, but
removing the key and adding it again will make it be last in the
iteration order.

**Notice:** Do not modify a map (add or remove keys) while an operation
is being performed on that map, for example in functions called during a
[forEach](../dart-core/map/foreach) or
[putIfAbsent](../dart-core/map/putifabsent) call, or while iterating the
map ([keys](../dart-core/map/keys), [values](../dart-core/map/values) or
[entries](../dart-core/map/entries)).

The keys of a `LinkedHashMap` must have consistent
[Object.==](../dart-core/object/operator_equals) and
[Object.hashCode](../dart-core/object/hashcode) implementations. This
means that the `==` operator must define a stable equivalence relation
on the keys (reflexive, symmetric, transitive, and consistent over
time), and that `hashCode` must be the same for objects that are
considered equal by `==`.

Example:

``` {.language-dart data-language="dart"}
final planetsByDiameter = {0.949: 'Venus'}; // A new LinkedHashMap
```

To add data to a map, use
[operator\[\]=](../dart-core/map/operator_put),
[addAll](../dart-core/map/addall) or
[addEntries](../dart-core/map/addentries).

``` {.language-dart data-language="dart"}
planetsByDiameter[1] = 'Earth';
planetsByDiameter.addAll({0.532: 'Mars', 11.209: 'Jupiter'});
```

To check if the map is empty, use [isEmpty](../dart-core/map/isempty) or
[isNotEmpty](../dart-core/map/isnotempty). To find the number of map
entries, use [length](../dart-core/map/length).

``` {.language-dart data-language="dart"}
print(planetsByDiameter.isEmpty); // false
print(planetsByDiameter.length); // 4
print(planetsByDiameter);
// {0.949: Venus, 1.0: Earth, 0.532: Mars, 11.209: Jupiter}
```

The [forEach](../dart-core/map/foreach) method calls a function for each
key/value entry of the map.

``` {.language-dart data-language="dart"}
planetsByDiameter.forEach((key, value) {
  print('$key \t $value');
  // 0.949    Venus
  // 1.0      Earth
  // 0.532    Mars
  // 11.209   Jupiter
});
```

To check whether the map has an entry with a specific key, use
[containsKey](../dart-core/map/containskey).

``` {.language-dart data-language="dart"}
final keyOneExists = planetsByDiameter.containsKey(1); // true
final keyFiveExists = planetsByDiameter.containsKey(5); // false
```

To check whether the map has an entry with a specific value, use
[containsValue](../dart-core/map/containsvalue).

``` {.language-dart data-language="dart"}
final earthExists = planetsByDiameter.containsValue('Earth'); // true
final saturnExists =  planetsByDiameter.containsValue('Saturn'); // false
```

To remove an entry with a specific key, use
[remove](../dart-core/map/remove).

``` {.language-dart data-language="dart"}
final removedValue = planetsByDiameter.remove(1);
print(removedValue); // Earth
print(planetsByDiameter); // {0.949: Venus, 0.532: Mars, 11.209: Jupiter}
```

To remove multiple entries at the same time, based on their keys and
values, use [removeWhere](../dart-core/map/removewhere).

``` {.language-dart data-language="dart"}
planetsByDiameter.removeWhere((key, value) => key == 0.949);
print(planetsByDiameter); // {0.532: Mars, 11.209: Jupiter}
```

To conditionally add or modify a value for a specific key, depending on
whether there already is an entry with that key, use
[putIfAbsent](../dart-core/map/putifabsent) or
[update](../dart-core/map/update).

``` {.language-dart data-language="dart"}
planetsByDiameter.update(0.949, (v) => 'Venus', ifAbsent: () => 'Venus');
planetsByDiameter.putIfAbsent(0.532, () => "Another Mars if needed");
print(planetsByDiameter); // {0.532: Mars, 11.209: Jupiter, 0.949: Venus}
```

To update the values of all keys, based on the existing key and value,
use [updateAll](../dart-core/map/updateall).

``` {.language-dart data-language="dart"}
planetsByDiameter.updateAll((key, value) => 'X');
print(planetsByDiameter); // {0.532: X, 11.209: X, 0.949: X}
```

To remove all entries and empty the map, use
[clear](../dart-core/map/clear).

``` {.language-dart data-language="dart"}
planetsByDiameter.clear();
print(planetsByDiameter); // {}
print(planetsByDiameter.isEmpty); // true
```

**See also:**

-   [Map](../dart-core/map-class), the general interface of key/value
    pair collections.
-   [HashMap](hashmap-class) is unordered (the order of iteration is not
    guaranteed).
-   [SplayTreeMap](splaytreemap-class) iterates the keys in sorted
    order.

Implemented types

:   -   [Map](../dart-core/map-class)\<K, V\>

Constructors
------------

[LinkedHashMap](linkedhashmap/linkedhashmap)({[bool](../dart-core/bool-class)
equals(K, K)?, [int](../dart-core/int-class) hashCode(K)?,
[bool](../dart-core/bool-class) isValidKey(dynamic)?})

::: {.constructor-modifier .features}
factory
:::

Creates an insertion-ordered hash-table based
[Map](../dart-core/map-class).

[LinkedHashMap.from](linkedhashmap/linkedhashmap.from)([Map](../dart-core/map-class)
other)

::: {.constructor-modifier .features}
factory
:::

Creates a [LinkedHashMap](linkedhashmap-class) that contains all key
value pairs of `other`.

[LinkedHashMap.fromEntries](linkedhashmap/linkedhashmap.fromentries)([Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<K,
V\>\> entries)

::: {.constructor-modifier .features}
factory
:::

Creates a [LinkedHashMap](linkedhashmap-class) containing the entries of
`entries`.

[LinkedHashMap.fromIterable](linkedhashmap/linkedhashmap.fromiterable)([Iterable](../dart-core/iterable-class)
iterable, {K key(dynamic element)?, V value(dynamic element)?})

::: {.constructor-modifier .features}
factory
:::

Creates a [LinkedHashMap](linkedhashmap-class) where the keys and values
are computed from the `iterable`.

[LinkedHashMap.fromIterables](linkedhashmap/linkedhashmap.fromiterables)([Iterable](../dart-core/iterable-class)\<K\>
keys, [Iterable](../dart-core/iterable-class)\<V\> values)

::: {.constructor-modifier .features}
factory
:::

Creates a [LinkedHashMap](linkedhashmap-class) associating the given
`keys` to `values`.

[LinkedHashMap.identity](linkedhashmap/linkedhashmap.identity)()

::: {.constructor-modifier .features}
factory
:::

Creates an insertion-ordered identity-based map.

[LinkedHashMap.of](linkedhashmap/linkedhashmap.of)([Map](../dart-core/map-class)\<K,
V\> other)

::: {.constructor-modifier .features}
factory
:::

Creates a [LinkedHashMap](linkedhashmap-class) that contains all key
value pairs of `other`. Example:

Properties {#instance-properties}
----------

[entries](../dart-core/map/entries) →
[Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<K,
V\>\>

::: {.features}
read-only, inherited
:::

The map entries of [this](linkedhashmap-class).

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

The keys of [this](linkedhashmap-class).

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

The values of [this](linkedhashmap-class).

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
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedHashMap-class.html>
:::
