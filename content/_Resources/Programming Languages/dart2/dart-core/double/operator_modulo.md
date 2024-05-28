[dart:core](../../dart-core/dart-core-library){._links-link}

operator % method
=================

::: {.section .multi-line-signature}
[double](../double-class) operator %(

1.  [num](../num-class) other

)

::: {.features}
override
:::
:::

Euclidean modulo of this number by `other`.

Returns the remainder of the Euclidean division. The Euclidean division
of two integers `a` and `b` yields two integers `q` and `r` such that
`a == b * q + r` and `0 <= r < b.abs()`.

The Euclidean division is only defined for integers, but can be easily
extended to work with doubles. In that case, `q` is still an integer,
but `r` may have a non-integer value that still satisfies
`0 <= r < |b|`.

The sign of the returned value `r` is always positive.

See [remainder](remainder) for the remainder of the truncating division.

The result is an [int](../int-class), as described by
[int.%](../num/operator_modulo), if both this number and `other` are
integers, otherwise the result is a [double](../double-class).

Example:

``` {.language-dart data-language="dart"}
print(5 % 3); // 2
print(-5 % 3); // 1
print(5 % -3); // 2
print(-5 % -3); // 1
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
double operator %(num other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/double/operator_modulo.html>
:::
