[dart:collection](../../dart-collection/dart-collection-library){._links-link}

SplayTreeMap\<K, V\> constructor
================================

::: {.section .multi-line-signature}
SplayTreeMap\<K, V\>(

1.  \[[int](../../dart-core/int-class) compare(
    1.  K key1,
    2.  K key2

    )?,
2.  [bool](../../dart-core/bool-class) isValidKey(
    1.  dynamic potentialKey

    )?\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
SplayTreeMap(
    [int Function(K key1, K key2)? compare,
    bool Function(dynamic potentialKey)? isValidKey])
    : _compare = compare ?? _defaultCompare<K>(),
      _validKey = isValidKey ?? ((dynamic a) => a is K);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeMap/SplayTreeMap.html>
:::
