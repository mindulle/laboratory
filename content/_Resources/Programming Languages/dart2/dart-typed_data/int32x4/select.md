[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

select method
=============

::: {.section .multi-line-signature}
[Float32x4](../float32x4-class) select(

1.  [Float32x4](../float32x4-class) trueValue,
2.  [Float32x4](../float32x4-class) falseValue

)
:::

Merge `trueValue` and `falseValue` based on [this](../int32x4-class)\'
bit mask: Select bit from `trueValue` when bit in
[this](../int32x4-class) is on. Select bit from `falseValue` when bit in
[this](../int32x4-class) is off.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Float32x4 select(Float32x4 trueValue, Float32x4 falseValue);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Int32x4/select.html>
:::
