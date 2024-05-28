[dart:core](../../dart-core/dart-core-library){._links-link}

operator \<\< method
====================

::: {.section .multi-line-signature}
[BigInt](../bigint-class) operator \<\<(

1.  [int](../int-class) shiftAmount

)
:::

Shift the bits of this integer to the left by `shiftAmount`.

Shifting to the left makes the number larger, effectively multiplying
the number by `pow(2, shiftIndex)`.

There is no limit on the size of the result. It may be relevant to limit
intermediate values by using the \"and\" operator with a suitable mask.

It is an error if `shiftAmount` is negative.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
BigInt operator <<(int shiftAmount);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/operator_shift_left.html>
:::
