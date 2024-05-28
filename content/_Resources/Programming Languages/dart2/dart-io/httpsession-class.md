[dart:io](../dart-io/dart-io-library){._links-link}

HttpSession class
=================

The [HttpRequest.session](httprequest/session) of an
[HttpRequest](httprequest-class).

Implemented types

:   -   [Map](../dart-core/map-class)

Constructors
------------

[HttpSession](httpsession/httpsession)()

Properties {#instance-properties}
----------

[entries](../dart-core/map/entries) →
[Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\>

::: {.features}
read-only, inherited
:::

The map entries of [this](httpsession-class).

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[id](httpsession/id) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

The id of the current session.

[isEmpty](../dart-core/map/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether there is no key/value pair in the map.

[isNew](httpsession/isnew) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Whether the session has not yet been sent to the client.

[isNotEmpty](../dart-core/map/isnotempty) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether there is at least one key/value pair in the map.

[keys](../dart-core/map/keys) → [Iterable](../dart-core/iterable-class)

::: {.features}
read-only, inherited
:::

The keys of [this](httpsession-class).

[length](../dart-core/map/length) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The number of key/value pairs in the map.

[onTimeout](httpsession/ontimeout) ← void Function()

::: {.features}
write-only
:::

Sets a callback that will be called when the session is timed out.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[values](../dart-core/map/values) →
[Iterable](../dart-core/iterable-class)

::: {.features}
read-only, inherited
:::

The values of [this](httpsession-class).

Methods {#instance-methods}
-------

[addAll](../dart-core/map/addall)([Map](../dart-core/map-class) other) →
void

::: {.features}
inherited
:::

Adds all key/value pairs of `other` to this map.

[addEntries](../dart-core/map/addentries)([Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\>
newEntries) → void

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

[destroy](httpsession/destroy)() → void

Destroys the session.

[forEach](../dart-core/map/foreach)(void action(dynamic key, dynamic
value)) → void

::: {.features}
inherited
:::

Applies `action` to each key/value pair of the map.

[map](../dart-core/map/map)\<K2,
V2\>([MapEntry](../dart-core/mapentry-class)\<K2, V2\> convert(dynamic
key, dynamic value)) → [Map](../dart-core/map-class)\<K2, V2\>

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

[putIfAbsent](../dart-core/map/putifabsent)(dynamic key, dynamic
ifAbsent()) → dynamic

::: {.features}
inherited
:::

Look up the value of `key`, or add a new entry if it isn\'t there.

[remove](../dart-core/map/remove)([Object](../dart-core/object-class)?
key) → dynamic

::: {.features}
inherited
:::

Removes `key` and its associated value, if present, from the map.

[removeWhere](../dart-core/map/removewhere)([bool](../dart-core/bool-class)
test(dynamic key, dynamic value)) → void

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

[update](../dart-core/map/update)(dynamic key, dynamic update(dynamic
value), {dynamic ifAbsent()?}) → dynamic

::: {.features}
inherited
:::

Updates the value for the provided `key`.

[updateAll](../dart-core/map/updateall)(dynamic update(dynamic key,
dynamic value)) → void

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
key) → dynamic

::: {.features}
inherited
:::

The value for the given `key`, or `null` if `key` is not in the map.

[operator \[\]=](../dart-core/map/operator_put)(dynamic key, dynamic
value) → void

::: {.features}
inherited
:::

Associates the `key` with the given `value`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpSession-class.html>
:::
