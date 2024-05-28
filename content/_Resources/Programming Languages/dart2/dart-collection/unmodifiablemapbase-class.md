[dart:collection](../dart-collection/dart-collection-library){._links-link}

UnmodifiableMapBase\<K, V\> class
=================================

Basic implementation of an unmodifiable [Map](../dart-core/map-class).

This class has a basic implementation of all but two of the members of
an unmodifiable [Map](../dart-core/map-class). A simple unmodifiable
`Map` class can be implemented by extending this class and implementing
`keys` and `operator[]`.

Modifying operations throw when used. The remaining non-modifying
operations are implemented in terms of `keys` and `operator[]`.

The `keys` iterable should have efficient
[Iterable.length](../dart-core/iterable/length) and
[Iterable.contains](../dart-core/iterable/contains) operations, and it
should catch concurrent modifications of the keys while iterating.

A more efficient implementation is usually possible by overriding some
of the other members as well.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [MapMixin](mapmixin-class)\<K, V\>
    -   [MapBase](mapbase-class)\<K, V\>
    -   UnmodifiableMapBase

Constructors
------------

[UnmodifiableMapBase](unmodifiablemapbase/unmodifiablemapbase)()

Properties {#instance-properties}
----------

[entries](mapmixin/entries) →
[Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<K,
V\>\>

::: {.features}
read-only, inherited
:::

The map entries of [this](unmodifiablemapbase-class).

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](mapmixin/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether there is no key/value pair in the map.

[isNotEmpty](mapmixin/isnotempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether there is at least one key/value pair in the map.

[keys](mapmixin/keys) → [Iterable](../dart-core/iterable-class)\<K\>

::: {.features}
read-only, inherited
:::

The keys of [this](unmodifiablemapbase-class).

[length](mapmixin/length) → [int](../dart-core/int-class)

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

[values](mapmixin/values) → [Iterable](../dart-core/iterable-class)\<V\>

::: {.features}
read-only, inherited
:::

The values of [this](unmodifiablemapbase-class).

Methods {#instance-methods}
-------

[addAll](unmodifiablemapbase/addall)([Map](../dart-core/map-class)\<K,
V\> other) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

[addEntries](unmodifiablemapbase/addentries)([Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<K,
V\>\> entries) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

[cast](mapmixin/cast)\<RK, RV\>() → [Map](../dart-core/map-class)\<RK,
RV\>

::: {.features}
inherited
:::

Provides a view of this map as having `RK` keys and `RV` instances, if
necessary.

[clear](unmodifiablemapbase/clear)() → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

[containsKey](mapmixin/containskey)([Object](../dart-core/object-class)?
key) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether this map contains the given `key`.

[containsValue](mapmixin/containsvalue)([Object](../dart-core/object-class)?
value) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether this map contains the given `value`.

[forEach](mapmixin/foreach)(void action(K key, V value)) → void

::: {.features}
inherited
:::

Applies `action` to each key/value pair of the map.

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

[putIfAbsent](unmodifiablemapbase/putifabsent)(K key, V ifAbsent()) → V

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

[remove](unmodifiablemapbase/remove)([Object](../dart-core/object-class)?
key) → V?

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

[removeWhere](unmodifiablemapbase/removewhere)([bool](../dart-core/bool-class)
test(K key, V value)) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

[toString](mapmixin/tostring)() → [String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[update](unmodifiablemapbase/update)(K key, V update(V value), {V
ifAbsent()?}) → V

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

[updateAll](unmodifiablemapbase/updateall)(V update(K key, V value)) →
void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

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
\[\]](mapmixin/operator_get)([Object](../dart-core/object-class)? key) →
V?

::: {.features}
inherited
:::

The value for the given `key`, or `null` if `key` is not in the map.

[operator \[\]=](unmodifiablemapbase/operator_put)(K key, V value) →
void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableMapBase-class.html>
:::
