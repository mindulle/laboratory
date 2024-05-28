[dart:collection](../../dart-collection/dart-collection-library){._links-link}

SplayTreeMap\<K, V\>.fromIterable constructor
=============================================

::: {.section .multi-line-signature}
SplayTreeMap\<K, V\>.fromIterable(

1.  [Iterable](../../dart-core/iterable-class) iterable,
2.  {K key(
    1.  dynamic element

    )?,
3.  V value(
    1.  dynamic element

    )?,
4.  [int](../../dart-core/int-class) compare(
    1.  K key1,
    2.  K key2

    )?,
5.  [bool](../../dart-core/bool-class) isValidKey(
    1.  dynamic potentialKey

    )?}

)
:::

Creates a [SplayTreeMap](../splaytreemap-class) where the keys and
values are computed from the `iterable`.

For each element of the `iterable` this constructor computes a key/value
pair, by applying `key` and `value` respectively.

The keys of the key/value pairs do not need to be unique. The last
occurrence of a key will simply overwrite any previous value.

If no functions are specified for `key` and `value`, the default is to
use the iterable value itself. Example:

``` {.language-dart data-language="dart"}
final numbers = [12, 11, 14, 13];
final mapFromIterable =
    SplayTreeMap<int, int>.fromIterable(numbers,
        key: (i) => i, value: (i) => i * i);
print(mapFromIterable); // {11: 121, 12: 144, 13: 169, 14: 196}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory SplayTreeMap.fromIterable(Iterable iterable,
    {K Function(dynamic element)? key,
    V Function(dynamic element)? value,
    int Function(K key1, K key2)? compare,
    bool Function(dynamic potentialKey)? isValidKey}) {
  SplayTreeMap<K, V> map = SplayTreeMap<K, V>(compare, isValidKey);
  MapBase._fillMapWithMappedIterable(map, iterable, key, value);
  return map;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeMap/SplayTreeMap.fromIterable.html>
:::
