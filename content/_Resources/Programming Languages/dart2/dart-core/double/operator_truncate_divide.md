[dart:core](../../dart-core/dart-core-library){._links-link}

operator \~/ method
===================

::: {.section .multi-line-signature}
[int](../int-class) operator \~/(

1.  [num](../num-class) other

)

::: {.features}
override
:::
:::

Truncating division operator.

Performs truncating division of this number by `other`. Truncating
division is division where a fractional result is converted to an
integer by rounding towards zero.

If both operands are [int](../int-class)s, then `other` must not be
zero. Then `a ~/ b` corresponds to `a.remainder(b)` such that
`a == (a ~/ b) * b + a.remainder(b)`.

If either operand is a [double](../double-class), then the other operand
is converted to a double before performing the division and truncation
of the result. Then `a ~/ b` is equivalent to `(a / b).truncate()`. This
means that the intermediate result of the double division must be a
finite integer (not an infinity or [double.nan](nan-constant)).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int operator ~/(num other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/double/operator_truncate_divide.html>
:::
