[dart:core](../dart-core/dart-core-library){._links-link}

Map\<K, V\> class
=================

A collection of key/value pairs, from which you retrieve a value using
its associated key.

There is a finite number of keys in the map, and each key has exactly
one value associated with it.

Maps, and their keys and values, can be iterated. The order of iteration
is defined by the individual type of map. Examples:

-   The plain [HashMap](../dart-collection/hashmap-class) is unordered
    (no order is guaranteed),
-   the [LinkedHashMap](../dart-collection/linkedhashmap-class) iterates
    in key insertion order,
-   and a sorted map like
    [SplayTreeMap](../dart-collection/splaytreemap-class) iterates the
    keys in sorted order.

It is generally not allowed to modify the map (add or remove keys) while
an operation is being performed on the map, for example in functions
called during a [forEach](map/foreach) or [putIfAbsent](map/putifabsent)
call. Modifying the map while iterating the keys or values may also
break the iteration.

It is generally not allowed to modify the equality of keys (and thus not
their hashcode) while they are in the map. Some specialized subtypes may
be more permissive, in which case they should document this behavior.

Implementers

:   -   [HashMap](../dart-collection/hashmap-class)
    -   [HttpSession](../dart-io/httpsession-class)
    -   [LinkedHashMap](../dart-collection/linkedhashmap-class)
    -   [MapMixin](../dart-collection/mapmixin-class)
    -   [MapView](../dart-collection/mapview-class)
    -   [UnmodifiableMapBase](../dart-collection/unmodifiablemapbase-class)
    -   [UnmodifiableMapView](../dart-collection/unmodifiablemapview-class)

Constructors
------------

[Map](map/map)()

::: {.constructor-modifier .features}
factory
:::

Creates an empty
[LinkedHashMap](../dart-collection/linkedhashmap-class).

[Map.from](map/map.from)([Map](map-class) other)

::: {.constructor-modifier .features}
factory
:::

Creates a [LinkedHashMap](../dart-collection/linkedhashmap-class) with
the same keys and values as `other`.

[Map.fromEntries](map/map.fromentries)([Iterable](iterable-class)\<[MapEntry](mapentry-class)\<K,
V\>\> entries)

::: {.constructor-modifier .features}
factory
:::

Creates a new map and adds all entries.

[Map.fromIterable](map/map.fromiterable)([Iterable](iterable-class)
iterable, {K key(dynamic element)?, V value(dynamic element)?})

::: {.constructor-modifier .features}
factory
:::

Creates a Map instance in which the keys and values are computed from
the `iterable`.

[Map.fromIterables](map/map.fromiterables)([Iterable](iterable-class)\<K\>
keys, [Iterable](iterable-class)\<V\> values)

::: {.constructor-modifier .features}
factory
:::

Creates a map associating the given `keys` to the given `values`.

[Map.identity](map/map.identity)()

::: {.constructor-modifier .features}
factory
:::

Creates an identity map with the default implementation,
[LinkedHashMap](../dart-collection/linkedhashmap-class).

[Map.of](map/map.of)([Map](map-class)\<K, V\> other)

::: {.constructor-modifier .features}
factory
:::

Creates a [LinkedHashMap](../dart-collection/linkedhashmap-class) with
the same keys and values as `other`.

[Map.unmodifiable](map/map.unmodifiable)([Map](map-class) other)

::: {.constructor-modifier .features}
factory
:::

Creates an unmodifiable hash-based map containing the entries of
`other`.

Properties {#instance-properties}
----------

[entries](map/entries) →
[Iterable](iterable-class)\<[MapEntry](mapentry-class)\<K, V\>\>

::: {.features}
read-only
:::

The map entries of [this](map-class).

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](map/isempty) → [bool](bool-class)

::: {.features}
read-only
:::

Whether there is no key/value pair in the map.

[isNotEmpty](map/isnotempty) → [bool](bool-class)

::: {.features}
read-only
:::

Whether there is at least one key/value pair in the map.

[keys](map/keys) → [Iterable](iterable-class)\<K\>

::: {.features}
read-only
:::

The keys of [this](map-class).

[length](map/length) → [int](int-class)

::: {.features}
read-only
:::

The number of key/value pairs in the map.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[values](map/values) → [Iterable](iterable-class)\<V\>

::: {.features}
read-only
:::

The values of [this](map-class).

Methods {#instance-methods}
-------

[addAll](map/addall)([Map](map-class)\<K, V\> other) → void

Adds all key/value pairs of `other` to this map.

[addEntries](map/addentries)([Iterable](iterable-class)\<[MapEntry](mapentry-class)\<K,
V\>\> newEntries) → void

Adds all key/value pairs of `newEntries` to this map.

[cast](map/cast)\<RK, RV\>() → [Map](map-class)\<RK, RV\>

Provides a view of this map as having `RK` keys and `RV` instances, if
necessary.

[clear](map/clear)() → void

Removes all entries from the map.

[containsKey](map/containskey)([Object](object-class)? key) →
[bool](bool-class)

Whether this map contains the given `key`.

[containsValue](map/containsvalue)([Object](object-class)? value) →
[bool](bool-class)

Whether this map contains the given `value`.

[forEach](map/foreach)(void action(K key, V value)) → void

Applies `action` to each key/value pair of the map.

[map](map/map)\<K2, V2\>([MapEntry](mapentry-class)\<K2, V2\> convert(K
key, V value)) → [Map](map-class)\<K2, V2\>

Returns a new map where all entries of this map are transformed by the
given `convert` function.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[putIfAbsent](map/putifabsent)(K key, V ifAbsent()) → V

Look up the value of `key`, or add a new entry if it isn\'t there.

[remove](map/remove)([Object](object-class)? key) → V?

Removes `key` and its associated value, if present, from the map.

[removeWhere](map/removewhere)([bool](bool-class) test(K key, V value))
→ void

Removes all entries of this map that satisfy the given `test`.

[toString](object/tostring)() → [String](string-class)

::: {.features}
inherited
:::

A string representation of this object.

[update](map/update)(K key, V update(V value), {V ifAbsent()?}) → V

Updates the value for the provided `key`.

[updateAll](map/updateall)(V update(K key, V value)) → void

Updates all values.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator \[\]](map/operator_get)([Object](object-class)? key) → V?

The value for the given `key`, or `null` if `key` is not in the map.

[operator \[\]=](map/operator_put)(K key, V value) → void

Associates the `key` with the given `value`.

Static Methods
--------------

[castFrom](map/castfrom)\<K, V, K2, V2\>([Map](map-class)\<K, V\> source) → [Map](map-class)\<K2, V2\>
:   Adapts `source` to be a `Map<K2, V2>`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Map-class.html>
:::
