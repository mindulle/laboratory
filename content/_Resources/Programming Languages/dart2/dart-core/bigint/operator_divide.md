[dart:core](../../dart-core/dart-core-library){._links-link}

operator / method
=================

::: {.section .multi-line-signature}
[double](../double-class) operator /(

1.  [BigInt](../bigint-class) other

)
:::

Double division operator.

Matching the similar operator on [int](../int-class), this operation
first performs [toDouble](todouble) on both this big integer and
`other`, then does [double.operator/](../double/operator_divide) on
those values and returns the result.

**Note:** The initial [toDouble](todouble) conversion may lose
precision.

Example:

``` {.language-dart data-language="dart"}
print(BigInt.from(1) / BigInt.from(2)); // 0.5
print(BigInt.from(1.99999) / BigInt.from(2)); // 0.5
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
double operator /(BigInt other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/operator_divide.html>
:::
