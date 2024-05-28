[dart:core](../dart-core/dart-core-library){._links-link}

MapEntry\<K, V\> class
======================

A key/value pair representing an entry in a [Map](map-class).

The [Map](map-class) interface contains various methods that can inspect
or modify the map based on entry objects.

``` {.language-dart data-language="dart"}
final map = {'1': 'A', '2': 'B'};
map.addEntries([
 MapEntry('3', 'C'),
 MapEntry('4', 'D'),
]);
print(map); // {1: A, 2: B, 3: C, 4: D}
```

Constructors
------------

[MapEntry](mapentry/mapentry)(K key, V value)

::: {.constructor-modifier .features}
const
:::

::: {.constructor-modifier .features}
factory
:::

Creates an entry with `key` and `value`.

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[key](mapentry/key) → K

::: {.features}
final
:::

The key of the entry.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[value](mapentry/value) → V

::: {.features}
final
:::

The value associated to [key](mapentry/key) in the map.

Methods {#instance-methods}
-------

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](mapentry/tostring)() → [String](string-class)

::: {.features}
override
:::

A string representation of this object.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/MapEntry-class.html>
:::
