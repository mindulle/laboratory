[dart:html](../dart-html/dart-html-library){._links-link}

Storage class
=============

The type used by the [Window.localStorage](window/localstorage) and
[Window.sessionStorage](window/sessionstorage) properties. Storage is
implemented as a Map\<String, String\>.

To store and get values, use Dart\'s built-in map syntax:

``` {.language-dart data-language="dart"}
window.localStorage['key1'] = 'val1';
window.localStorage['key2'] = 'val2';
window.localStorage['key3'] = 'val3';
assert(window.localStorage['key3'] == 'val3');
```

You can use [Map](https://api.dart.dev/stable/dart-core/Map-class.html)
APIs such as containsValue(), clear(), and length:

``` {.language-dart data-language="dart"}
assert(window.localStorage.containsValue('does not exist') == false);
window.localStorage.clear();
assert(window.localStorage.length == 0);
```

Mixed in types

:   -   [MapMixin](../dart-collection/mapmixin-class)\<[String](../dart-core/string-class),
        [String](../dart-core/string-class)\>

Annotations

:   -   \@Unstable()
    -   \@Native(\"Storage\")

Properties {#instance-properties}
----------

[entries](../dart-collection/mapmixin/entries) →
[Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)\>\>

::: {.features}
read-only, inherited
:::

The map entries of [this](storage-class).

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](storage/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether there is no key/value pair in the map.

[isNotEmpty](storage/isnotempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether there is at least one key/value pair in the map.

[keys](storage/keys) →
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>

::: {.features}
read-only, override
:::

The keys of [this](storage-class).

[length](storage/length) → [int](../dart-core/int-class)

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

[values](storage/values) →
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>

::: {.features}
read-only, override
:::

The values of [this](storage-class).

Methods {#instance-methods}
-------

[addAll](storage/addall)([Map](../dart-core/map-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)\> other) → void

::: {.features}
override
:::

Adds all key/value pairs of `other` to this map.

[addEntries](../dart-collection/mapmixin/addentries)([Iterable](../dart-core/iterable-class)\<[MapEntry](../dart-core/mapentry-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)\>\> newEntries) → void

::: {.features}
inherited
:::

Adds all key/value pairs of `newEntries` to this map.

[cast](../dart-collection/mapmixin/cast)\<RK, RV\>() →
[Map](../dart-core/map-class)\<RK, RV\>

::: {.features}
inherited
:::

Provides a view of this map as having `RK` keys and `RV` instances, if
necessary.

[clear](storage/clear)() → void

::: {.features}
override
:::

Removes all entries from the map.

[containsKey](storage/containskey)([Object](../dart-core/object-class)?
key) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether this map contains the given `key`.

[containsValue](storage/containsvalue)([Object](../dart-core/object-class)?
value) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether this map contains the given `value`.

[forEach](storage/foreach)(void f([String](../dart-core/string-class)
key, [String](../dart-core/string-class) value)) → void

::: {.features}
override
:::

Applies `action` to each key/value pair of the map.

[map](../dart-collection/mapmixin/map)\<K2,
V2\>([MapEntry](../dart-core/mapentry-class)\<K2, V2\>
transform([String](../dart-core/string-class) key,
[String](../dart-core/string-class) value)) →
[Map](../dart-core/map-class)\<K2, V2\>

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

[putIfAbsent](storage/putifabsent)([String](../dart-core/string-class)
key, [String](../dart-core/string-class) ifAbsent()) →
[String](../dart-core/string-class)

::: {.features}
override
:::

Look up the value of `key`, or add a new entry if it isn\'t there.

[remove](storage/remove)([Object](../dart-core/object-class)? key) →
[String](../dart-core/string-class)?

::: {.features}
override
:::

Removes `key` and its associated value, if present, from the map.

[removeWhere](../dart-collection/mapmixin/removewhere)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) key,
[String](../dart-core/string-class) value)) → void

::: {.features}
inherited
:::

Removes all entries of this map that satisfy the given `test`.

[toString](../dart-collection/mapmixin/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[update](../dart-collection/mapmixin/update)([String](../dart-core/string-class)
key, [String](../dart-core/string-class)
update([String](../dart-core/string-class) value),
{[String](../dart-core/string-class) ifAbsent()?}) →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

Updates the value for the provided `key`.

[updateAll](../dart-collection/mapmixin/updateall)([String](../dart-core/string-class)
update([String](../dart-core/string-class) key,
[String](../dart-core/string-class) value)) → void

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
\[\]](storage/operator_get)([Object](../dart-core/object-class)? key) →
[String](../dart-core/string-class)?

::: {.features}
override
:::

The value for the given `key`, or `null` if `key` is not in the map.

[operator
\[\]=](storage/operator_put)([String](../dart-core/string-class) key,
[String](../dart-core/string-class) value) → void

::: {.features}
override
:::

Associates the `key` with the given `value`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Storage-class.html>
:::
