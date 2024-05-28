[dart:collection](../../dart-collection/dart-collection-library){._links-link}

putIfAbsent method
==================

::: {.section .multi-line-signature}
V putIfAbsent(

1.  K key,
2.  V ifAbsent( )

)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable map.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
V putIfAbsent(K key, V ifAbsent()) {
  throw UnsupportedError("Cannot modify unmodifiable map");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableMapView/putIfAbsent.html>
:::
