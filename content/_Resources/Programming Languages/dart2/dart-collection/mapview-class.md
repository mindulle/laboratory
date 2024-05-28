[dart:collection](../dart-collection/dart-collection-library){._links-link}

MapView\<K, V\> class
=====================

Wrapper around a class that implements [Map](../dart-core/map-class)
that only exposes `Map` members.

A simple wrapper that delegates all `Map` members to the map provided in
the constructor.

Base for delegating map implementations like
[UnmodifiableMapView](unmodifiablemapview-class).

Implemented types

:   -   [Map](../dart-core/map-class)\<K, V\>

Implementers

:   -   [UnmodifiableMapView](unmodifiablemapview-class)

Constructors
------------

[MapView](mapview/mapview)([Map](../dart-core/map-class)\<K, V\> map)

::: {.constructor-modifier .features}
const
:::

Properties {#instance-properties}
----------

[entries](mapview/entries) →
[Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<K,
V\>\>

::: {.features}
read-only, override
:::

The map entries of [this](mapview-class).

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](mapview/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether there is no key/value pair in the map.

[isNotEmpty](mapview/isnotempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether there is at least one key/value pair in the map.

[keys](mapview/keys) → [Iterable](../dart-core/iterable-class)\<K\>

::: {.features}
read-only, override
:::

The keys of [this](mapview-class).

[length](mapview/length) → [int](../dart-core/int-class)

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

[values](mapview/values) → [Iterable](../dart-core/iterable-class)\<V\>

::: {.features}
read-only, override
:::

The values of [this](mapview-class).

Methods {#instance-methods}
-------

[addAll](mapview/addall)([Map](../dart-core/map-class)\<K, V\> other) →
void

::: {.features}
override
:::

Adds all key/value pairs of `other` to this map.

[addEntries](mapview/addentries)([Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<K,
V\>\> entries) → void

::: {.features}
override
:::

Adds all key/value pairs of `newEntries` to this map.

[cast](mapview/cast)\<RK, RV\>() → [Map](../dart-core/map-class)\<RK,
RV\>

::: {.features}
override
:::

Provides a view of this map as having `RK` keys and `RV` instances, if
necessary.

[clear](mapview/clear)() → void

::: {.features}
override
:::

Removes all entries from the map.

[containsKey](mapview/containskey)([Object](../dart-core/object-class)?
key) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether this map contains the given `key`.

[containsValue](mapview/containsvalue)([Object](../dart-core/object-class)?
value) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether this map contains the given `value`.

[forEach](mapview/foreach)(void action(K key, V value)) → void

::: {.features}
override
:::

Applies `action` to each key/value pair of the map.

[map](mapview/map)\<K2,
V2\>([MapEntry](../dart-core/mapentry-class)\<K2, V2\> transform(K key,
V value)) → [Map](../dart-core/map-class)\<K2, V2\>

::: {.features}
override
:::

Returns a new map where all entries of this map are transformed by the
given `convert` function.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[putIfAbsent](mapview/putifabsent)(K key, V ifAbsent()) → V

::: {.features}
override
:::

Look up the value of `key`, or add a new entry if it isn\'t there.

[remove](mapview/remove)([Object](../dart-core/object-class)? key) → V?

::: {.features}
override
:::

Removes `key` and its associated value, if present, from the map.

[removeWhere](mapview/removewhere)([bool](../dart-core/bool-class)
test(K key, V value)) → void

::: {.features}
override
:::

Removes all entries of this map that satisfy the given `test`.

[toString](mapview/tostring)() → [String](../dart-core/string-class)

::: {.features}
override
:::

A string representation of this object.

[update](mapview/update)(K key, V update(V value), {V ifAbsent()?}) → V

::: {.features}
override
:::

Updates the value for the provided `key`.

[updateAll](mapview/updateall)(V update(K key, V value)) → void

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
\[\]](mapview/operator_get)([Object](../dart-core/object-class)? key) →
V?

::: {.features}
override
:::

The value for the given `key`, or `null` if `key` is not in the map.

[operator \[\]=](mapview/operator_put)(K key, V value) → void

::: {.features}
override
:::

Associates the `key` with the given `value`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/MapView-class.html>
:::
