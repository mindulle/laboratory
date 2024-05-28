[dart:core](../../dart-core/dart-core-library){._links-link}

operator & method
=================

::: {.section .multi-line-signature}
[BigInt](../bigint-class) operator &(

1.  [BigInt](../bigint-class) other

)
:::

Bit-wise and operator.

Treating both `this` and `other` as sufficiently large two\'s component
integers, the result is a number with only the bits set that are set in
both `this` and `other`

Of both operands are negative, the result is negative, otherwise the
result is non-negative.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
BigInt operator &(BigInt other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/operator_bitwise_and.html>
:::
