[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

add method
==========

::: {.section .multi-line-signature}
void add(

1.  [Float32x4](../float32x4-class) value

)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void add(E value) {
  throw new UnsupportedError("Cannot add to an unmodifiable list");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableFloat32x4ListView/add.html>
:::
