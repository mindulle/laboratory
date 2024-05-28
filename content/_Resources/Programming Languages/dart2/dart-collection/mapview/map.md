[dart:collection](../../dart-collection/dart-collection-library){._links-link}

map\<K2, V2\> method
====================

::: {.section .multi-line-signature}
[Map](../../dart-core/map-class)\<K2, V2\> map\<K2, V2\>(

1.  [MapEntry](../../dart-core/mapentry-class)\<K2, V2\> transform(
    1.  K key,
    2.  V value

    )

)

::: {.features}
override
:::
:::

Returns a new map where all entries of this map are transformed by the
given `convert` function.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Map<K2, V2> map<K2, V2>(MapEntry<K2, V2> transform(K key, V value)) =>
    _map.map<K2, V2>(transform);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/MapView/map.html>
:::
