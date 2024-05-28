[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

removeAt method
===============

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) removeAt(

1.  [int](../../dart-core/int-class) index

)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
E removeAt(int index) {
  throw new UnsupportedError("Cannot remove from an unmodifiable list");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableUint32ListView/removeAt.html>
:::
