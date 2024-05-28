[dart:core](../../dart-core/dart-core-library){._links-link}

bitLength property
==================

::: {#getter .section .multi-line-signature}
[int](../int-class) bitLength
:::

Returns the minimum number of bits required to store this big integer.

The number of bits excludes the sign bit, which gives the natural length
for non-negative (unsigned) values. Negative values are complemented to
return the bit position of the first bit that differs from the sign bit.

To find the number of bits needed to store the value as a signed value,
add one, i.e. use `x.bitLength + 1`.

``` {.language-dart data-language="dart"}
x.bitLength == (-x-1).bitLength;

BigInt.from(3).bitLength == 2;   // 00000011
BigInt.from(2).bitLength == 2;   // 00000010
BigInt.from(1).bitLength == 1;   // 00000001
BigInt.from(0).bitLength == 0;   // 00000000
BigInt.from(-1).bitLength == 0;  // 11111111
BigInt.from(-2).bitLength == 1;  // 11111110
BigInt.from(-3).bitLength == 2;  // 11111101
BigInt.from(-4).bitLength == 2;  // 11111100
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get bitLength;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/bitLength.html>
:::
