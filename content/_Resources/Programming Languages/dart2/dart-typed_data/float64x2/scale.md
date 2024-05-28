[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

scale method
============

::: {.section .multi-line-signature}
[Float64x2](../float64x2-class) scale(

1.  [double](../../dart-core/double-class) s

)
:::

Returns a copy of [this](../float64x2-class) each lane being scaled by
`s`. Equivalent to this \* new Float64x2.splat(s)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Float64x2 scale(double s);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Float64x2/scale.html>
:::
