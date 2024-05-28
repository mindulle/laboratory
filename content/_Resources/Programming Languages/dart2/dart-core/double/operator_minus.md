[dart:core](../../dart-core/dart-core-library){._links-link}

operator - method
=================

::: {.section .multi-line-signature}
[double](../double-class) operator -(

1.  [num](../num-class) other

)

::: {.features}
override
:::
:::

Subtracts `other` from this number.

The result is an [int](../int-class), as described by
[int.-](../num/operator_minus), if both this number and `other` is an
integer, otherwise the result is a [double](../double-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
double operator -(num other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/double/operator_minus.html>
:::
