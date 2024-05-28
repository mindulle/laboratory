[dart:collection](../../dart-collection/dart-collection-library){._links-link}

updateAll method
================

::: {.section .multi-line-signature}
void updateAll(

1.  V update(
    1.  K key,
    2.  V value

    )

)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable map.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void updateAll(V update(K key, V value)) {
  throw UnsupportedError("Cannot modify unmodifiable map");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableMapBase/updateAll.html>
:::
