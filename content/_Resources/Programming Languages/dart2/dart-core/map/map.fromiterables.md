[dart:core](../../dart-core/dart-core-library){._links-link}

Map\<K, V\>.fromIterables constructor
=====================================

::: {.section .multi-line-signature}
Map\<K, V\>.fromIterables(

1.  [Iterable](../iterable-class)\<K\> keys,
2.  [Iterable](../iterable-class)\<V\> values

)
:::

Creates a map associating the given `keys` to the given `values`.

The map construction iterates over `keys` and `values` simultaneously,
and adds an entry to the map for each pair of key and value.

``` {.language-dart data-language="dart"}
final rings = <bool>[false, false, true, true];
final planets = <String>{'Earth', 'Mars', 'Jupiter', 'Saturn'};
final map = Map<String, bool>.fromIterables(planets, rings);
print(map); // {Earth: false, Mars: false, Jupiter: true, Saturn: true}
```

If `keys` contains the same object multiple times, the value of the last
occurrence overwrites any previous value.

The two [Iterable](../iterable-class)s must have the same length.

The created map is a
[LinkedHashMap](../../dart-collection/linkedhashmap-class). A
`LinkedHashMap` requires the keys to implement compatible `operator==`
and `hashCode`. It iterates in key insertion order.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Map.fromIterables(Iterable<K> keys, Iterable<V> values) =
    LinkedHashMap<K, V>.fromIterables;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Map/Map.fromIterables.html>
:::
