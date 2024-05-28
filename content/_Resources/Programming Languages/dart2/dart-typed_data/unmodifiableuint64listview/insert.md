[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

insert method
=============

::: {.section .multi-line-signature}
void insert(

1.  [int](../../dart-core/int-class) index,
2.  [int](../../dart-core/int-class) element

)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void insert(int index, E element) {
  throw new UnsupportedError("Cannot add to an unmodifiable list");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableUint64ListView/insert.html>
:::
