[dart:collection](../../dart-collection/dart-collection-library){._links-link}

HashMap\<K, V\>.fromIterables constructor
=========================================

::: {.section .multi-line-signature}
HashMap\<K, V\>.fromIterables(

1.  [Iterable](../../dart-core/iterable-class)\<K\> keys,
2.  [Iterable](../../dart-core/iterable-class)\<V\> values

)
:::

Creates a [HashMap](../hashmap-class) associating the given `keys` to
`values`.

This constructor iterates over `keys` and `values` and maps each element
of `keys` to the corresponding element of `values`.

If `keys` contains the same object multiple times, the last occurrence
overwrites the previous value.

It is an error if the two [Iterable](../../dart-core/iterable-class)s
don\'t have the same length. Example:

``` {.language-dart data-language="dart"}
final keys = ['Mercury', 'Venus', 'Earth', 'Mars'];
final values = [0.06, 0.81, 1, 0.11];
final mapFromIterables = HashMap.fromIterables(keys, values);
print(mapFromIterables);
// {Earth: 1, Mercury: 0.06, Mars: 0.11, Venus: 0.81}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory HashMap.fromIterables(Iterable<K> keys, Iterable<V> values) {
  HashMap<K, V> map = HashMap<K, V>();
  MapBase._fillMapWithIterables(map, keys, values);
  return map;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/HashMap/HashMap.fromIterables.html>
:::
