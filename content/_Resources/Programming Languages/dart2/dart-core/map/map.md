[dart:core](../../dart-core/dart-core-library){._links-link}

Map\<K, V\> constructor
=======================

::: {.section .multi-line-signature}
Map\<K, V\>()
:::

Creates an empty
[LinkedHashMap](../../dart-collection/linkedhashmap-class).

This constructor is equivalent to the non-const map literal `<K,V>{}`.

A `LinkedHashMap` requires the keys to implement compatible `operator==`
and `hashCode`. It iterates in key insertion order.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory Map();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Map/Map.html>
:::
