[dart:collection](../../dart-collection/dart-collection-library){._links-link}

entries property
================

::: {#getter .section .multi-line-signature}
[Iterable](../../dart-core/iterable-class)\<[MapEntry](../../dart-core/mapentry-class)\<K,
V\>\> entries

::: {.features}
override
:::
:::

The map entries of [this](../splaytreemap-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterable<MapEntry<K, V>> get entries =>
    _SplayTreeMapEntryIterable<K, V>(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeMap/entries.html>
:::
