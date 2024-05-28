[dart:collection](../../dart-collection/dart-collection-library){._links-link}

addEntries method
=================

::: {.section .multi-line-signature}
void addEntries(

1.  [Iterable](../../dart-core/iterable-class)\<[MapEntry](../../dart-core/mapentry-class)\<K,
    V\>\> entries

)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable map.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addEntries(Iterable<MapEntry<K, V>> entries) {
  throw UnsupportedError("Cannot modify unmodifiable map");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableMapView/addEntries.html>
:::
