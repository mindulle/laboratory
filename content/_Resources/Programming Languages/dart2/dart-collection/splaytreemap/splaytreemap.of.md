[dart:collection](../../dart-collection/dart-collection-library){._links-link}

SplayTreeMap\<K, V\>.of constructor
===================================

::: {.section .multi-line-signature}
SplayTreeMap\<K, V\>.of(

1.  [Map](../../dart-core/map-class)\<K, V\> other,
2.  \[[int](../../dart-core/int-class) compare(
    1.  K key1,
    2.  K key2

    )?,
3.  [bool](../../dart-core/bool-class) isValidKey(
    1.  dynamic potentialKey

    )?\]

)
:::

Creates a [SplayTreeMap](../splaytreemap-class) that contains all
key/value pairs of `other`. Example:

``` {.language-dart data-language="dart"}
final baseMap = <int, String>{3: 'A', 2: 'B', 1: 'C', 4: 'D'};
final mapOf = SplayTreeMap<num, Object>.of(baseMap);
print(mapOf); // {1: C, 2: B, 3: A, 4: D}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory SplayTreeMap.of(Map<K, V> other,
        [int Function(K key1, K key2)? compare,
        bool Function(dynamic potentialKey)? isValidKey]) =>
    SplayTreeMap<K, V>(compare, isValidKey)..addAll(other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeMap/SplayTreeMap.of.html>
:::
