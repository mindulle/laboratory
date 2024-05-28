[dart:collection](../../dart-collection/dart-collection-library){._links-link}

LinkedHashMap\<K, V\>.fromIterables constructor
===============================================

::: {.section .multi-line-signature}
LinkedHashMap\<K, V\>.fromIterables(

1.  [Iterable](../../dart-core/iterable-class)\<K\> keys,
2.  [Iterable](../../dart-core/iterable-class)\<V\> values

)
:::

Creates a [LinkedHashMap](../linkedhashmap-class) associating the given
`keys` to `values`.

This constructor iterates over `keys` and `values` and maps each element
of `keys` to the corresponding element of `values`.

If `keys` contains the same object multiple times, the last occurrence
overwrites the previous value.

It is an error if the two [Iterable](../../dart-core/iterable-class)s
don\'t have the same length. Example:

``` {.language-dart data-language="dart"}
final values = [0.06, 0.81, 1, 0.11];
final keys = ['Mercury', 'Venus', 'Earth', 'Mars'];
final mapFromIterables = LinkedHashMap.fromIterables(keys, values);
print(mapFromIterables);
// {Mercury: 0.06, Venus: 0.81, Earth: 1, Mars: 0.11}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory LinkedHashMap.fromIterables(Iterable<K> keys, Iterable<V> values) {
  LinkedHashMap<K, V> map = LinkedHashMap<K, V>();
  MapBase._fillMapWithIterables(map, keys, values);
  return map;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedHashMap/LinkedHashMap.fromIterables.html>
:::
