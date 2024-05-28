[dart:core](../../dart-core/dart-core-library){._links-link}

operator \~ method
==================

::: {.section .multi-line-signature}
[int](../int-class) operator \~()
:::

The bit-wise negate operator.

Treating `this` as a sufficiently large two\'s component integer, the
result is a number with the opposite bits set.

This maps any integer `x` to `-x - 1`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int operator ~();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/int/operator_bitwise_negate.html>
:::
