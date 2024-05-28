[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

length property
===============

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) length

::: {.features}
inherited
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get length => _list.length;
```

::: {#setter .section .multi-line-signature}
void length=([int](../../dart-core/int-class) newLength)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set length(int newLength) {
  throw new UnsupportedError(
      "Cannot change the length of an unmodifiable list");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableUint64ListView/length.html>
:::
