[dart:core](../../dart-core/dart-core-library){._links-link}

operator \<\< method
====================

::: {.section .multi-line-signature}
[int](../int-class) operator \<\<(

1.  [int](../int-class) shiftAmount

)
:::

Shift the bits of this integer to the left by `shiftAmount`.

Shifting to the left makes the number larger, effectively multiplying
the number by `pow(2, shiftAmount)`.

There is no limit on the size of the result. It may be relevant to limit
intermediate values by using the \"and\" operator with a suitable mask.

It is an error if `shiftAmount` is negative.

Example:

``` {.language-dart data-language="dart"}
print((3 << 1).toRadixString(2)); // 0011 -> 0110
print((9 << 2).toRadixString(2)); // 1001 -> 100100
print((10 << 3).toRadixString(2)); // 1010 -> 1010000
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int operator <<(int shiftAmount);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/int/operator_shift_left.html>
:::
