[dart:core](../../dart-core/dart-core-library){._links-link}

Map\<K, V\>.unmodifiable constructor
====================================

::: {.section .multi-line-signature}
Map\<K, V\>.unmodifiable(

1.  [Map](../map-class) other

)
:::

Creates an unmodifiable hash-based map containing the entries of
`other`.

The keys must all be instances of `K` and the values of `V`. The `other`
map itself can have any type.

The map requires the keys to implement compatible `operator==` and
`hashCode`. The created map iterates keys in a fixed order, preserving
the order provided by `other`.

The resulting map behaves like the result of [Map.from](map.from),
except that the map returned by this constructor is not modifiable.

``` {.language-dart data-language="dart"}
final planets = <int, String>{1: 'Mercury', 2: 'Venus', 3: 'Earth'};
final unmodifiableMap = Map.unmodifiable(planets);
unmodifiableMap[4] = 'Mars'; // Throws
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory Map.unmodifiable(Map<dynamic, dynamic> other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Map/Map.unmodifiable.html>
:::
