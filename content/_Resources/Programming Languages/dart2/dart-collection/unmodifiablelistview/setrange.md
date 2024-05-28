[dart:collection](../../dart-collection/dart-collection-library){._links-link}

setRange method
===============

::: {.section .multi-line-signature}
void setRange(

1.  [int](../../dart-core/int-class) start,
2.  [int](../../dart-core/int-class) end,
3.  [Iterable](../../dart-core/iterable-class)\<E\> iterable,
4.  \[[int](../../dart-core/int-class) skipCount = 0\]

)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setRange(int start, int end, Iterable<E> iterable, [int skipCount = 0]) {
  throw new UnsupportedError("Cannot modify an unmodifiable list");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableListView/setRange.html>
:::
