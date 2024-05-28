[dart:core](../../dart-core/dart-core-library){._links-link}

operator \>\> method
====================

::: {.section .multi-line-signature}
[BigInt](../bigint-class) operator \>\>(

1.  [int](../int-class) shiftAmount

)
:::

Shift the bits of this integer to the right by `shiftAmount`.

Shifting to the right makes the number smaller and drops the least
significant bits, effectively doing an integer division by
`pow(2, shiftIndex)`.

It is an error if `shiftAmount` is negative.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
BigInt operator >>(int shiftAmount);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/operator_shift_right.html>
:::
