[dart:core](../../dart-core/dart-core-library){._links-link}

Map\<K, V\>.of constructor
==========================

::: {.section .multi-line-signature}
Map\<K, V\>.of(

1.  [Map](../map-class)\<K, V\> other

)
:::

Creates a [LinkedHashMap](../../dart-collection/linkedhashmap-class)
with the same keys and values as `other`.

A `LinkedHashMap` requires the keys to implement compatible `operator==`
and `hashCode`, and it allows `null` as a key. It iterates in key
insertion order.

``` {.language-dart data-language="dart"}
final planets = <int, String>{1: 'Mercury', 2: 'Venus', 3: 'Earth'};
final mapOf = Map<num, String>.of(planets);
print(mapOf); // {1: Mercury, 2: Venus, 3: Earth}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Map.of(Map<K, V> other) = LinkedHashMap<K, V>.of;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Map/Map.of.html>
:::
