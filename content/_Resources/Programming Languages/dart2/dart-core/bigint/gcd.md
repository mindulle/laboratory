[dart:core](../../dart-core/dart-core-library){._links-link}

gcd method
==========

::: {.section .multi-line-signature}
[BigInt](../bigint-class) gcd(

1.  [BigInt](../bigint-class) other

)
:::

Returns the greatest common divisor of this big integer and `other`.

If either number is non-zero, the result is the numerically greatest
integer dividing both `this` and `other`.

The greatest common divisor is independent of the order, so `x.gcd(y)`
is always the same as `y.gcd(x)`.

For any integer `x`, `x.gcd(x)` is `x.abs()`.

If both `this` and `other` is zero, the result is also zero.

Example:

``` {.language-dart data-language="dart"}
print(BigInt.from(4).gcd(BigInt.from(2))); // 2
print(BigInt.from(8).gcd(BigInt.from(4))); // 4
print(BigInt.from(10).gcd(BigInt.from(12))); // 2
print(BigInt.from(10).gcd(BigInt.from(10))); // 10
print(BigInt.from(-2).gcd(BigInt.from(-3))); // 1
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
BigInt gcd(BigInt other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/gcd.html>
:::
