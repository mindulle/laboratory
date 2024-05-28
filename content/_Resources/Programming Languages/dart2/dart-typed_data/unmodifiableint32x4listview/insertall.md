[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

insertAll method
================

::: {.section .multi-line-signature}
void insertAll(

1.  [int](../../dart-core/int-class) at,
2.  [Iterable](../../dart-core/iterable-class)\<[Int32x4](../int32x4-class)\>
    iterable

)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void insertAll(int at, Iterable<E> iterable) {
  throw new UnsupportedError("Cannot add to an unmodifiable list");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableInt32x4ListView/insertAll.html>
:::
