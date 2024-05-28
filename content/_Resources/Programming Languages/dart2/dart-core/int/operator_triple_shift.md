[dart:core](../../dart-core/dart-core-library){._links-link}

operator \>\>\> method
======================

::: {.section .multi-line-signature}
[int](../int-class) operator \>\>\>(

1.  [int](../int-class) shiftAmount

)
:::

Bitwise unsigned right shift by `shiftAmount` bits.

The least significant `shiftAmount` bits are dropped, the remaining bits
(if any) are shifted down, and zero-bits are shifted in as the new most
significant bits.

The `shiftAmount` must be non-negative.

Example:

``` {.language-dart data-language="dart"}
print((3 >>> 1).toRadixString(2)); // 0011 -> 0001
print((9 >>> 2).toRadixString(2)); // 1001 -> 0010
print(((-9) >>> 2).toRadixString(2)); // 111...1011 -> 001...1110 (> 0)
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int operator >>>(int shiftAmount);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/int/operator_triple_shift.html>
:::
