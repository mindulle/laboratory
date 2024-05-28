[dart:collection](../../dart-collection/dart-collection-library){._links-link}

LinkedHashMap\<K, V\>.identity constructor
==========================================

::: {.section .multi-line-signature}
LinkedHashMap\<K, V\>.identity()
:::

Creates an insertion-ordered identity-based map.

Effectively shorthand for:

``` {.language-dart data-language="dart"}
LinkedHashMap<K, V>(equals: identical,
                    hashCode: identityHashCode)
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory LinkedHashMap.identity();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedHashMap/LinkedHashMap.identity.html>
:::
