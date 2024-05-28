[dart:collection](../../dart-collection/dart-collection-library){._links-link}

LinkedHashMap\<K, V\>.of constructor
====================================

::: {.section .multi-line-signature}
LinkedHashMap\<K, V\>.of(

1.  [Map](../../dart-core/map-class)\<K, V\> other

)
:::

Creates a [LinkedHashMap](../linkedhashmap-class) that contains all key
value pairs of `other`. Example:

``` {.language-dart data-language="dart"}
final baseMap = <int, String> {3: 'A', 2: 'B', 1: 'C', 4: 'D'};
final mapOf = LinkedHashMap<num, Object>.of(baseMap);
print(mapOf); // {3: A, 2: B, 1: C, 4: D}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory LinkedHashMap.of(Map<K, V> other) =>
    LinkedHashMap<K, V>()..addAll(other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedHashMap/LinkedHashMap.of.html>
:::
