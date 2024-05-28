[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

operator + method
=================

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[Float64x2](../float64x2-class)\>
operator +(

1.  [List](../../dart-core/list-class)\<[Float64x2](../float64x2-class)\>
    other

)

::: {.features}
override
:::
:::

Returns the concatenation of this list and `other`.

If `other` is also a [Float64x2List](../float64x2list-class), the result
is a new [Float64x2List](../float64x2list-class), otherwise the result
is a normal growable `List<Float64x2>`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<Float64x2> operator +(List<Float64x2> other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Float64x2List/operator_plus.html>
:::
