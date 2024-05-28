[dart:collection](../dart-collection/dart-collection-library){._links-link}

MapMixin\<K, V\> class
======================

Mixin implementing a [Map](../dart-core/map-class).

This mixin has a basic implementation of all but five of the members of
[Map](../dart-core/map-class). A basic `Map` class can be implemented by
mixin in this class and implementing `keys`, `operator[]`,
`operator[]=`, `remove` and `clear`. The remaining operations are
implemented in terms of these five.

The `keys` iterable should have efficient
[Iterable.length](../dart-core/iterable/length) and
[Iterable.contains](../dart-core/iterable/contains) operations, and it
should catch concurrent modifications of the keys while iterating.

A more efficient implementation is usually possible by overriding some
of the other members as well.

Implemented types

:   -   [Map](../dart-core/map-class)\<K, V\>

Implementers

:   -   [AudioParamMap](../dart-web_audio/audioparammap-class)
    -   [MapBase](mapbase-class)
    -   [MidiInputMap](../dart-html/midiinputmap-class)
    -   [MidiOutputMap](../dart-html/midioutputmap-class)
    -   [RtcStatsReport](../dart-html/rtcstatsreport-class)
    -   [SplayTreeMap](splaytreemap-class)
    -   [Storage](../dart-html/storage-class)

Constructors
------------

[MapMixin](mapmixin/mapmixin)()

Properties {#instance-properties}
----------

[entries](mapmixin/entries) →
[Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<K,
V\>\>

::: {.features}
read-only, override
:::

The map entries of [this](mapmixin-class).

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](mapmixin/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether there is no key/value pair in the map.

[isNotEmpty](mapmixin/isnotempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether there is at least one key/value pair in the map.

[keys](mapmixin/keys) → [Iterable](../dart-core/iterable-class)\<K\>

::: {.features}
read-only, override
:::

The keys of [this](mapmixin-class).

[length](mapmixin/length) → [int](../dart-core/int-class)

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

[values](mapmixin/values) → [Iterable](../dart-core/iterable-class)\<V\>

::: {.features}
read-only, override
:::

The values of [this](mapmixin-class).

Methods {#instance-methods}
-------

[addAll](mapmixin/addall)([Map](../dart-core/map-class)\<K, V\> other) →
void

::: {.features}
override
:::

Adds all key/value pairs of `other` to this map.

[addEntries](mapmixin/addentries)([Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<K,
V\>\> newEntries) → void

::: {.features}
override
:::

Adds all key/value pairs of `newEntries` to this map.

[cast](mapmixin/cast)\<RK, RV\>() → [Map](../dart-core/map-class)\<RK,
RV\>

::: {.features}
override
:::

Provides a view of this map as having `RK` keys and `RV` instances, if
necessary.

[clear](mapmixin/clear)() → void

::: {.features}
override
:::

Removes all entries from the map.

[containsKey](mapmixin/containskey)([Object](../dart-core/object-class)?
key) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether this map contains the given `key`.

[containsValue](mapmixin/containsvalue)([Object](../dart-core/object-class)?
value) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether this map contains the given `value`.

[forEach](mapmixin/foreach)(void action(K key, V value)) → void

::: {.features}
override
:::

Applies `action` to each key/value pair of the map.

[map](mapmixin/map)\<K2,
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

[putIfAbsent](mapmixin/putifabsent)(K key, V ifAbsent()) → V

::: {.features}
override
:::

Look up the value of `key`, or add a new entry if it isn\'t there.

[remove](mapmixin/remove)([Object](../dart-core/object-class)? key) → V?

::: {.features}
override
:::

Removes `key` and its associated value, if present, from the map.

[removeWhere](mapmixin/removewhere)([bool](../dart-core/bool-class)
test(K key, V value)) → void

::: {.features}
override
:::

Removes all entries of this map that satisfy the given `test`.

[toString](mapmixin/tostring)() → [String](../dart-core/string-class)

::: {.features}
override
:::

A string representation of this object.

[update](mapmixin/update)(K key, V update(V value), {V ifAbsent()?}) → V

::: {.features}
override
:::

Updates the value for the provided `key`.

[updateAll](mapmixin/updateall)(V update(K key, V value)) → void

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
\[\]](mapmixin/operator_get)([Object](../dart-core/object-class)? key) →
V?

::: {.features}
override
:::

The value for the given `key`, or `null` if `key` is not in the map.

[operator \[\]=](mapmixin/operator_put)(K key, V value) → void

::: {.features}
override
:::

Associates the `key` with the given `value`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/MapMixin-class.html>
:::
