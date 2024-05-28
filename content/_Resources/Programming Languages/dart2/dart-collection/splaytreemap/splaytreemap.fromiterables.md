[dart:collection](../../dart-collection/dart-collection-library){._links-link}

SplayTreeMap\<K, V\>.fromIterables constructor
==============================================

::: {.section .multi-line-signature}
SplayTreeMap\<K, V\>.fromIterables(

1.  [Iterable](../../dart-core/iterable-class)\<K\> keys,
2.  [Iterable](../../dart-core/iterable-class)\<V\> values,
3.  \[[int](../../dart-core/int-class) compare(
    1.  K key1,
    2.  K key2

    )?,
4.  [bool](../../dart-core/bool-class) isValidKey(
    1.  dynamic potentialKey

    )?\]

)
:::

Creates a [SplayTreeMap](../splaytreemap-class) associating the given
`keys` to `values`.

This constructor iterates over `keys` and `values` and maps each element
of `keys` to the corresponding element of `values`.

If `keys` contains the same object multiple times, the last occurrence
overwrites the previous value.

It is an error if the two [Iterable](../../dart-core/iterable-class)s
don\'t have the same length. Example:

``` {.language-dart data-language="dart"}
final keys = ['1', '2', '3', '4'];
final values = ['A', 'B', 'C', 'D'];
final mapFromIterables = SplayTreeMap.fromIterables(keys, values);
print(mapFromIterables); // {1: A, 2: B, 3: C, 4: D}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory SplayTreeMap.fromIterables(Iterable<K> keys, Iterable<V> values,
    [int Function(K key1, K key2)? compare,
    bool Function(dynamic potentialKey)? isValidKey]) {
  SplayTreeMap<K, V> map = SplayTreeMap<K, V>(compare, isValidKey);
  MapBase._fillMapWithIterables(map, keys, values);
  return map;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeMap/SplayTreeMap.fromIterables.html>
:::
