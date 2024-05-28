[dart:core](../../dart-core/dart-core-library){._links-link}

operator \>\> method
====================

::: {.section .multi-line-signature}
[int](../int-class) operator \>\>(

1.  [int](../int-class) shiftAmount

)
:::

Shift the bits of this integer to the right by `shiftAmount`.

Shifting to the right makes the number smaller and drops the least
significant bits, effectively doing an integer division by
`pow(2, shiftAmount)`.

It is an error if `shiftAmount` is negative.

Example:

``` {.language-dart data-language="dart"}
print((3 >> 1).toRadixString(2)); // 0011 -> 0001
print((9 >> 2).toRadixString(2)); // 1001 -> 0010
print((10 >> 3).toRadixString(2)); // 1010 -> 0001
print((-6 >> 2).toRadixString); // 111...1010 -> 111...1110 == -2
print((-85 >> 3).toRadixString); // 111...10101011 -> 111...11110101 == -11
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int operator >>(int shiftAmount);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/int/operator_shift_right.html>
:::
