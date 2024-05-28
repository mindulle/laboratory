[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

shuffle method
==============

::: {.section .multi-line-signature}
void shuffle(

1.  \[[Random](../../dart-math/random-class)? random\]

)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void shuffle([Random? random]) {
  throw new UnsupportedError("Cannot modify an unmodifiable list");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableFloat32x4ListView/shuffle.html>
:::
