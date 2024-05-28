[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

clear method
============

::: {.section .multi-line-signature}
void clear()

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void clear() {
  throw new UnsupportedError("Cannot clear an unmodifiable list");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableInt32ListView/clear.html>
:::
