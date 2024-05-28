[dart:collection](../../dart-collection/dart-collection-library){._links-link}

HashMap\<K, V\>.of constructor
==============================

::: {.section .multi-line-signature}
HashMap\<K, V\>.of(

1.  [Map](../../dart-core/map-class)\<K, V\> other

)
:::

Creates a [HashMap](../hashmap-class) that contains all key/value pairs
of `other`. Example:

``` {.language-dart data-language="dart"}
final baseMap = <int, String>{1: 'A', 2: 'B', 3: 'C'};
final mapOf = HashMap<num, Object>.of(baseMap);
print(mapOf); // {1: A, 2: B, 3: C}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory HashMap.of(Map<K, V> other) => HashMap<K, V>()..addAll(other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/HashMap/HashMap.of.html>
:::
