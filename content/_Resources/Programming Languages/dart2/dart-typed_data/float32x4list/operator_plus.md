[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

operator + method
=================

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[Float32x4](../float32x4-class)\>
operator +(

1.  [List](../../dart-core/list-class)\<[Float32x4](../float32x4-class)\>
    other

)

::: {.features}
override
:::
:::

Returns the concatenation of this list and `other`.

If `other` is also a [Float32x4List](../float32x4list-class), the result
is a new [Float32x4List](../float32x4list-class), otherwise the result
is a normal growable `List<Float32x4>`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<Float32x4> operator +(List<Float32x4> other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Float32x4List/operator_plus.html>
:::
