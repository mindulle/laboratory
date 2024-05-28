[dart:collection](../../dart-collection/dart-collection-library){._links-link}

remove method
=============

::: {.section .multi-line-signature}
V? remove(

1.  [Object](../../dart-core/object-class)? key

)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable map.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
V? remove(Object? key) {
  throw UnsupportedError("Cannot modify unmodifiable map");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableMapView/remove.html>
:::
