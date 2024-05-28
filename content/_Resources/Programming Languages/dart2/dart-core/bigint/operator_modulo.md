[dart:core](../../dart-core/dart-core-library){._links-link}

operator % method
=================

::: {.section .multi-line-signature}
[BigInt](../bigint-class) operator %(

1.  [BigInt](../bigint-class) other

)
:::

Euclidean modulo operator.

Returns the remainder of the Euclidean division. The Euclidean division
of two integers `a` and `b` yields two integers `q` and `r` such that
`a == b * q + r` and `0 <= r < b.abs()`.

The sign of the returned value `r` is always positive.

See [remainder](remainder) for the remainder of the truncating division.

Example:

``` {.language-dart data-language="dart"}
print(BigInt.from(5) % BigInt.from(3)); // 2
print(BigInt.from(-5) % BigInt.from(3)); // 1
print(BigInt.from(5) % BigInt.from(-3)); // 2
print(BigInt.from(-5) % BigInt.from(-3)); // 1
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
BigInt operator %(BigInt other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt/operator_modulo.html>
:::
