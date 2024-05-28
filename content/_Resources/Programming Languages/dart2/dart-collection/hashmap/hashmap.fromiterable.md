[dart:collection](../../dart-collection/dart-collection-library){._links-link}

HashMap\<K, V\>.fromIterable constructor
========================================

::: {.section .multi-line-signature}
HashMap\<K, V\>.fromIterable(

1.  [Iterable](../../dart-core/iterable-class) iterable,
2.  {K key(
    1.  dynamic element

    )?,
3.  V value(
    1.  dynamic element

    )?}

)
:::

Creates a [HashMap](../hashmap-class) where the keys and values are
computed from the `iterable`.

For each element of the `iterable` this constructor computes a key/value
pair, by applying `key` and `value` respectively.

The keys of the key/value pairs do not need to be unique. The last
occurrence of a key will simply overwrite any previous value.

If no values are specified for `key` and `value`, the default is the
identity function. Example:

``` {.language-dart data-language="dart"}
final numbers = [11, 12, 13, 14];
final mapFromIterable = HashMap<int, int>.fromIterable(numbers,
    key: (i) => i, value: (i) => i * i);
print(mapFromIterable); // {11: 121, 12: 144, 13: 169, 14: 196}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory HashMap.fromIterable(Iterable iterable,
    {K Function(dynamic element)? key, V Function(dynamic element)? value}) {
  HashMap<K, V> map = HashMap<K, V>();
  MapBase._fillMapWithMappedIterable(map, iterable, key, value);
  return map;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/HashMap/HashMap.fromIterable.html>
:::
