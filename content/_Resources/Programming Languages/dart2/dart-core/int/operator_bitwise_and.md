[dart:core](../../dart-core/dart-core-library){._links-link}

operator & method
=================

::: {.section .multi-line-signature}
[int](../int-class) operator &(

1.  [int](../int-class) other

)
:::

Bit-wise and operator.

Treating both `this` and `other` as sufficiently large two\'s component
integers, the result is a number with only the bits set that are set in
both `this` and `other`

If both operands are negative, the result is negative, otherwise the
result is non-negative.

``` {.language-dart data-language="dart"}
print((2 & 1).toRadixString(2)); // 0010 & 0001 -> 0000
print((3 & 1).toRadixString(2)); // 0011 & 0001 -> 0001
print((10 & 2).toRadixString(2)); // 1010 & 0010 -> 0010
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int operator &(int other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/int/operator_bitwise_and.html>
:::
