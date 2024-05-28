[dart:collection](../../dart-collection/dart-collection-library){._links-link}

insertAll method
================

::: {.section .multi-line-signature}
void insertAll(

1.  [int](../../dart-core/int-class) at,
2.  [Iterable](../../dart-core/iterable-class)\<E\> iterable

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
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableListView/insertAll.html>
:::
