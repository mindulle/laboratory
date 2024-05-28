[dart:collection](../dart-collection/dart-collection-library){._links-link}

UnmodifiableMapView\<K, V\> class
=================================

View of a [Map](../dart-core/map-class) that disallow modifying the map.

A wrapper around a `Map` that forwards all members to the map provided
in the constructor, except for operations that modify the map. Modifying
operations throw instead.

``` {.language-dart data-language="dart"}
final baseMap = <int, String>{1: 'Mars', 2: 'Mercury', 3: 'Venus'};
final unmodifiableMapView = UnmodifiableMapView(baseMap);

// Remove an entry from the original map.
baseMap.remove(3);
print(unmodifiableMapView); // {1: Mars, 2: Mercury}

unmodifiableMapView.remove(1); // Throws.
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [MapView](mapview-class)\<K, V\>
    -   UnmodifiableMapView

Constructors
------------

[UnmodifiableMapView](unmodifiablemapview/unmodifiablemapview)([Map](../dart-core/map-class)\<K,
V\> map)

Properties {#instance-properties}
----------

[entries](mapview/entries) →
[Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<K,
V\>\>

::: {.features}
read-only, inherited
:::

The map entries of [this](unmodifiablemapview-class).

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](mapview/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether there is no key/value pair in the map.

[isNotEmpty](mapview/isnotempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether there is at least one key/value pair in the map.

[keys](mapview/keys) → [Iterable](../dart-core/iterable-class)\<K\>

::: {.features}
read-only, inherited
:::

The keys of [this](unmodifiablemapview-class).

[length](mapview/length) → [int](../dart-core/int-class)

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

[values](mapview/values) → [Iterable](../dart-core/iterable-class)\<V\>

::: {.features}
read-only, inherited
:::

The values of [this](unmodifiablemapview-class).

Methods {#instance-methods}
-------

[addAll](unmodifiablemapview/addall)([Map](../dart-core/map-class)\<K,
V\> other) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

[addEntries](unmodifiablemapview/addentries)([Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<K,
V\>\> entries) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

[cast](unmodifiablemapview/cast)\<RK, RV\>() →
[Map](../dart-core/map-class)\<RK, RV\>

::: {.features}
override
:::

Provides a view of this map as having `RK` keys and `RV` instances, if
necessary.

[clear](unmodifiablemapview/clear)() → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

[containsKey](mapview/containskey)([Object](../dart-core/object-class)?
key) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether this map contains the given `key`.

[containsValue](mapview/containsvalue)([Object](../dart-core/object-class)?
value) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether this map contains the given `value`.

[forEach](mapview/foreach)(void action(K key, V value)) → void

::: {.features}
inherited
:::

Applies `action` to each key/value pair of the map.

[map](mapview/map)\<K2,
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

[putIfAbsent](unmodifiablemapview/putifabsent)(K key, V ifAbsent()) → V

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

[remove](unmodifiablemapview/remove)([Object](../dart-core/object-class)?
key) → V?

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

[removeWhere](unmodifiablemapview/removewhere)([bool](../dart-core/bool-class)
test(K key, V value)) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

[toString](mapview/tostring)() → [String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[update](unmodifiablemapview/update)(K key, V update(V value), {V
ifAbsent()?}) → V

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

[updateAll](unmodifiablemapview/updateall)(V update(K key, V value)) →
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
\[\]](mapview/operator_get)([Object](../dart-core/object-class)? key) →
V?

::: {.features}
inherited
:::

The value for the given `key`, or `null` if `key` is not in the map.

[operator \[\]=](unmodifiablemapview/operator_put)(K key, V value) →
void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable map.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableMapView-class.html>
:::
